---
title: "Japanese BERT run_classifier reading"
---

- Run_classifier reading of [Japanese BERT
You are reading [https://github.com/yoheikikuta/bert-japanese/blob/master/src/run_classifier.py](https://github.com/yoheikikuta/bert-japanese/blob/master/src/run_classifier.py)
- The bert repository of the main house is imported with a git submodule.
    - I add it to sys.path and reuse it in import modeling or something.
    - The BERT model definition and other information is written there.
    - Related: [[Import is moved before sys.path setting in VSCode]].
- This run_classifier.py is based on the original run_classifier.py with modifications such as using SentencePiece

- tf.app.run() calls main
- main→model_fn_builder→create_model
- in create_model.
    - `model = modeling.BertModel(...)`
    - I'm working on a BERT model here.
        - Imported modeling from the original BERT repository.
        - BERT's network structure is defined there.
            - [https://github.com/google-research/bert/blob/88a817c37f788702a363ff935fd173b6dc6ac0d6/modeling.py#L31](https://github.com/google-research/bert/blob/88a817c37f788702a363ff935fd173b6dc6ac0d6/modeling.py#L31)
    - Comment
        - >  # In the demo, we are doing a simple classification task on the entire segment.
        - >  # If you want to use the token-level output, use model.get_sequence_output() instead.
        - Using get_pooled_output()
        - What is this?
            - A simple full concatenation layer that takes the output for the first token as input and produces the hidden_size output
python

```
# The "pooler" converts the encoded sequence tensor of shape
# [batch_size, seq_length, hidden_size] to a tensor of shape
# [batch_size, hidden_size]. This is necessary for segment-level
# (or segment-pair-level) classification tasks where we need a fixed
# dimensional representation of the segment.
     with tf.variable_scope("pooler"):
       # We "pool" the model by simply taking the hidden state corresponding
       # to the first token. We assume that this has been pre-trained
       first_token_tensor = tf.squeeze(self.sequence_output[:, 0:1, :], axis=1)
       self.pooled_output = tf.layers.dense(
           first_token_tensor,
           config.hidden_size,
           activation=tf.tanh,
           kernel_initializer=create_initializer(config.initializer_range))
```

        - I'm like, "What? You want the first token? Shouldn't it be the last token of the sentence?" but it is not correct.
            - RNN-like mental models are being dragged out.
            - BERT has a stacked [[self-caution]] structure
                - Each individual self-attention acts as a convolution of indefinite length for the lower layers
                - So it doesn't matter if it's at the beginning or the end of a sentence.
        - I thought the output of the first token would be packed with information about the word itself and the whole sentence, tough.
            - It's not right.
            - It is not a word because there is a CLS token at the beginning
                - `tokens:   [CLS] the dog is hairy . [SEP]`
                - [src](https://github.com/yoheikikuta/bert-japanese/blob/df61ef5065100c8f8df4f01728020e399b4326da/src/run_classifier.py#L283)
        - Discussion of whether the output to the first token can be interpreted as a vector embedding of the sentence.
            - [Features extracted from layer -1 represent sentence embedding for a sentence? · Issue #71 · google-research/bert](https://github.com/google-research/bert/issues/71)
                - Why not use the hidden state of the first token as default strategy, i.e. the `[CLS]`?
                    - [Frequently Asked Questions — bert-as-service 1.6.1 documentation](https://bert-as-service.readthedocs.io/en/latest/section/faq.html#why-not-use-the-hidden-state-of-the-first-token-as-default-strategy-i-e-the-cls)
                - Why not the last hidden layer? Why second-to-last?
                    - [Frequently Asked Questions — bert-as-service 1.6.1 documentation](https://bert-as-service.readthedocs.io/en/latest/section/faq.html#why-not-the-last-hidden-layer-why-second-to-last)
            - My conclusion came to NO: [[BERT statement vector]].
- l.728 `use_one_hot_embeddings=FLAGS.use_tpu)` Is this correct?
    - right
    - On TPU it is faster, and [src [https://github.com/yoheikikuta/bert-japanese/blob/59e306faffe8e77dbf7347c8bb75c09ecfa8a1dc/src/extract_features.](https://github.com/yoheikikuta/bert-japanese/blob/59e306faffe8e77dbf7347c8bb75c09ecfa8a1dc/src/extract_features.) py#L80].

- tf.flags is not in Tensorflow 2.0
    - `AttributeError: module 'tensorflow' has no attribute 'flags'`
    - Should be replaced by argparse

- To port to Tensorflow 2, there are rather many modifications, so I decided to create a TF 1 environment with venv because it's too much trouble
:

```
  python3 -m venv ./venv
  source ./venv/bin/activate
  pip install --upgrade pip
  pip install tensorflow==1.15rc2
  pip install -r ../requirements.txt
```


- tokenize
    - `tokenization_sentencepiece.FullTokenizer(model_file="../model/wiki-ja.model", vocab_file="../model/wiki-ja.vocab")`
    - `In [9]: tok.tokenize("Today is sunny", internal server error) `
    - `Out[9]: ['▁本', '日', 'ha', '晴', '天', 'なり', 'インター', 'nar', 'サーバー', 'error']`

- bert_config_file
    - --bert_config_file= ... config.json is not found in the repository.
    - There is a config.ini
    - Generating json from ini at the beginning of run_classifier.py
    - I decided to save this under the name config.json.

- ValueError: Couldn't find 'checkpoint' file or checkpoints in given directory ../model
    - Place the downloaded `model.ckpt-1400000.*` in . /model and put it in `--init_checkpoint=. /model`...
    - `--init_checkpoint=. /model/model.ckpt-1400000` is correct

- extract_feature.py worked.
    - The command looks like this
        - `$ python3 extract_features.py --model_file=../model/wiki-ja.model --vocab_file=../model/wiki-ja.vocab --input_file=smallinput.txt --bert_config_file=config.json --init_checkpoint=../model/model.ckpt-1400000 --output_file=tmp/output`
        - JSON is spit out with the file name specified in --output_file.
python

```
x = json.load(open("tmp/output"))
In [8]: x["features"][2]["token"]                                                                                                                      
Out[8]: 'correct'
In [10]: x["features"][2]["layers"][0]                                                                                                                 
Out[10]: 
{'index': -1,
 'values': [-0.433769, ...]}
```

        - Each token contains a vector of 768 dimensions.
            - (If you carelessly use it on a large file, you may end up with a very large JSON.)
        - For me, who wants a vector to a statement, can I just take out the vector of the first token of layer -1?

- read_examples
    - If separated by ` ||| `, it is considered as a pair of two sentences, otherwise it is considered as a single sentence
    - I was thinking that if you want to pour in your own data, it would be better to replace the part of main that calls read_examples instead of reading from the text.
        - Because I want to use Scrapbox JSON files as the source data.

- Imported extract_feature.py and overwrote main
    - 8245 seconds to vector 6343 cases
    - MacBook Pro (15-inch, 2018) / 2.6 GHz Intel Core i7 / 16 GB 2400 MHz DDR4

- Note on experiment: [[Link Creation Support]].

- I haven't tried additional learning and fine-tuning in run_classifier.py yet.
    - If you try it, write to [Japanese BERT fine-tuning

---
This page is auto-translated from [/nishio/日本語BERTのrun_classifier読解](https://scrapbox.io/nishio/日本語BERTのrun_classifier読解) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
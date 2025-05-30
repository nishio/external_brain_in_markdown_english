---
title: "Japanese BERT fine-tuning"
---

    - Do [[fine-tuning]] of [Japanese BERT
- I've even loaded a trained model of BERT on hand to vectorize the sentences and train a discriminative model.
    - It was 72.1%, so I want to experiment with fine-tuning this and see how far it goes up.
- Read this.
    - [https://github.com/yoheikikuta/bert-japanese/blob/master/notebook/finetune-to-livedoor-corpus.ipynb](https://github.com/yoheikikuta/bert-japanese/blob/master/notebook/finetune-to-livedoor-corpus.ipynb)
- Replicate finetune-to-livedoor-corpus.ipynb to your own Google Colab environment
- It says to gcutil cp from within GCP, but I decided to mount Google Drive.
        - [[View Drive from Google Colab]]
- Options for run_classifier:.
    - `--model_file=../model/wiki-ja.model \`
    - `--vocab_file=../model/wiki-ja.vocab \`
    - These specify the SentencePiece model.
        - If you follow the ipynb procedure, it is copied from GCP to Colab's FS in advance.
        - I'm not doing it, so I'll read from Google Drive.
        - like this
            - `--model_file=/content/gdrive/My\ Drive/bert-wiki-ja/wiki-ja.model \`
            - `--vocab_file=/content/gdrive/My\ Drive/bert-wiki-ja/wiki-ja.vocab \`
            - `--init_checkpoint=/content/gdrive/My\ Drive/bert-wiki-ja/model.ckpt-1400000 \`
        - Google Colab's FS root is /content.
            - I didn't want to make the mistake caused by relative paths, so I used absolute paths.
        - Note: BERT models must be loaded and results exported to GCP
            - init_checkpoint will fail if written above because TPU tries to read it.
                - [[Cannot write to Google Colab's local FS from TPU]]
- Where data is being read
    - `train_examples = processor.get_train_examples(FLAGS.data_dir)`
        - The processor is `processor = processors[task_name]()` and `--livedoorProcessor` is selected by `--task_name=livedoor` passed as a command line argument.
        - `LivedoorProcessor` extends `DataProcessor` and calls the class method `_read_tsv` of the parent class, which simply opens the file, reads it as TSV and returns each line in a list
        - The result is used to create an `InputExample` object in `LivedoorProcessor#_create_examples` and put it in the list.
        - `InputExample` with text and label
- Model Creation
    - `model_fn_builder(...) Create `model_fn` with `tf.contrib.tpu.TPUEstimator`, then wrap it with `tf.contrib.tpu.TPUEstimator` and call it `estimator`.
            - [[Where to read the learned model]]
        - `model_fn_builder(...) `call `create_model
        - This is done by creating the original BERT model and then `output_layer = model.get_pooled_output()`.
            - I explained what this `get_pooled_output` is in [[Japanese BERT run_classifier reading#5db89bb6aff09e0000d4c214]].
        - It looks like you are implementing a simple logistic regression with `get_pooled_output` as input, but I'm not sure why you had to implement it on your own.
        - I'd like to customize things in the future, but for now, I guess I'll just accept "that's the way it is" and move on.
        - The slight difference in my case this time is that the label is 0/1.
- mounting
    - Import run_clussifier.py and create your own `LivedoorProcessor` equivalent and rewrite main to call it!
    - Use the mapping from title(unique id) to body text in honbun_data.json
    - The `LivedoorProcessor` reads different files for each method call, but in my case one
        - Create data outside of the class and have methods just return references
    - Negative-positive pairs are in negaposi.json, so use these.
    - > I'd like to customize things in the future, but for now, I guess I'll just accept "that's the way it is" and move on.
        - I'm starting to think I can't do this.
        - It's not impossible, but implementing a negative-positive decision by receiving two pairs of values in LR is...
        - No quicksand because there is no combination predisposition...
        - Well, let's do it as a simple means to an end.
    - In the first place, do we need `pooled_output` for each of the two input sentences?
        - Should I put it in BERT text_a and text_b?
    - The original `_create_examples` does `tokenization.convert_to_unicode`, but in my case it's 0/1, so I guess I can put it in int.
- He died after a short run.
        - [[Cannot write to Google Colab's local FS from TPU]]
    - "service-***@cloud-tpu.iam.gserviceaccount.com does not have storage.objects.list access to ***.appspot.com."
        - The cell labeled "Check TPU" in ipynb even grants GCP Bucket access to the TPU
        - If it doesn't work, this is where you've failed and you need to start over.
:

```
***** Eval results *****
eval_accuracy = 0.9525939
eval_loss = 0.40050572
global_step = 1047
loss = 0.39979258
CPU times: user 2.1 s, sys: 313 ms, total: 2.41 s
Wall time: 7min 54s
```

classification_report

```
             precision    recall  f1-score   support

           0       0.94      0.96      0.95      1118
           1       0.95      0.94      0.95      1117

    accuracy                           0.95      2235
   macro avg       0.95      0.95      0.95      2235
weighted avg       0.95      0.95      0.95      2235
```

confusion_matrix

```
[[1068   50]
 [  68 1049]]
```

- It makes me want to spit on my eyebrows to see if it's true.

summary
- Fine-tuning of BERT with 6705 data can be done in about 7 minutes using TPU
- 72% to 95% accuracy
    - ![image](https://gyazo.com/e779e6a21c7867c92d9c4676110066cb/thumb/1000)
    - However, there is a problem that the results of processing B cannot be cached
        - I haven't measured it, but I'm concerned that the processing time will go up by an order of magnitude or two.
        - I want to try the right shape.
            - This is an addition caution
        - I want to try inner product attention and dimensionality reduction attention.
            - see [[CybozuHackathon2019]]

---
This page is auto-translated from [/nishio/日本語BERTのfine-tuning](https://scrapbox.io/nishio/日本語BERTのfine-tuning) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "BERT statement vector"
---

Discussion of whether it is good or bad to use the hidden state of the first token when using BERT to obtain a vector embedding of a sentence.

- create_pretraining_data.py
    - Pick a random sentence with approximately 0.5 probability at L271 and make it the second sentence.
        - [src](https://github.com/google-research/bert/blob/0fce551b55caabcfba52c61e18f34b541aef186a/create_pretraining_data.py#L271)
    - L130, L139, and whether it is a random sentence is written out as next_sentence_labels
        - [src](https://github.com/google-research/bert/blob/0fce551b55caabcfba52c61e18f34b541aef186a/create_pretraining_data.py#L139)
- run_pretraining.py
    - Calculating loss from model.get_pooled_output() and next_sentence_labels in L144
        - [src](https://github.com/google-research/bert/blob/e13c1f3459cc254f7abbabfc5a286a3304d573e4/run_pretraining.py#L144)
        - Specifically, it is calculated by get_next_sentence_output from L285
            - There is a weight matrix from the hidden_size dimension to the second dimension and a bias in the second dimension, which is multiplied by the input and added to the softmax
            - [src](https://github.com/google-research/bert/blob/e13c1f3459cc254f7abbabfc5a286a3304d573e4/run_pretraining.py#L285)
- modeling.py
    - This model.get_pooled_output() is the hidden state of the first token multiplied by dense once.
        - [src](https://github.com/google-research/bert/blob/master/modeling.py#L225)
- When solving the problem of identifying whether two sentences are aligned or random in the pre-training stage, by using only this 768-dimensional pooled_output, the "information to identify it" is enriched in this pooled_output.
    - To identify whether two sentences are aligned sentences or random sentences, "what topic the sentence is about" is extracted to determine whether the topics of the two sentences are identical, so by solving this identification, a "topic vector" is extracted
    - But in this network design, there is no guarantee that that "topic vector" will come to pooled_output
        - It is possible to finish identifying whether the topic is connected in the lower network and only "Yes/No" can come to pooled_output
        - This is due to the fact that the lower network has an attention mechanism that can refer to both statements
        - If embedding of sentences was desired, each sentence should have been trained in the pre-training phase with the opponent unseen, and the inner product of the pooled_output of each sentence should have been calculated and used for identification.
        - ![image](https://gyazo.com/3975480429dadf600bc752de564248bd/thumb/1000)
        - This should give you a vector in the pooled_output that would be appropriate to calculate the similarity by inner product.
        - It would have been better to learn with the right structure in the pre-training stage, but since it is expensive to redo the pre-training, it might be better to fine-tuning by solving the continuous sentence identification problem again with the right structure.

-----
- Do we need a sentence vector in the first place?
    - Isn't what you really want a vector of sentences consisting of multiple sentences?
    - Can I add another layer of self-attention?
    - Why not just fine-tuning it for the purpose you want to use it for, without thinking "let's make a sentence vector?"

---
This page is auto-translated from [/nishio/BERTの文ベクトル](https://scrapbox.io/nishio/BERTの文ベクトル) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
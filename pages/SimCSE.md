---
title: "SimCSE"
---

[SimCSE and Vector Search to Improve Convenience by Posting Similar Content (Case Study on Related Search Words in Yahoo! Search) - Yahoo! JAPAN Tech Blog](https://techblog.yahoo.co.jp/entry/2023050830422060/)
    - [[vector search]]
- > BERT has been shown to be effective and widely used for various tasks in natural language processing. However, it is considered inappropriate for tasks that use sentence vectors, such as this vector search. The reason is that BERT has been identified as having the characteristic of anisotropy [[2]]. This is that the sentence vectors are biased in a particular direction and thus fail to adequately capture word similarity.
- >  SimCSE eliminated the anisotropy by modifying the vectors of positive examples so that they are closer to each other and the distribution of the vectors is uniform.
        - [[BERT anisotropy]]

[(2104.08821) SimCSE: Simple Contrastive Learning of Sentence Embeddings](https://arxiv.org/abs/2104.08821)

[princeton-nlp/SimCSE: EMNLP'2021: SimCSE: Simple Contrastive Learning of Sentence Embeddings](https://github.com/princeton-nlp/SimCSE)


[https://www.slideshare.net/DeepLearningJP2016/dlsimcse-simple-contrastive-learning-of-sentence-embeddings-emnlp-2021](https://www.slideshare.net/DeepLearningJP2016/dlsimcse-simple-contrastive-learning-of-sentence-embeddings-emnlp-2021)

Comparison with BERT
- anisotropy

embedding
[[Embedding]]

---
This page is auto-translated from [/nishio/SimCSE](https://scrapbox.io/nishio/SimCSE) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
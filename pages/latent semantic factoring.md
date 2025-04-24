---
title: "latent semantic factoring"
---

- Latent Semantic Analysis: [[Latent Semantic Analysis]], [[LSA]]
- Latent Semantic Indexing or Latent Semantic Index: [[Latent Semantic Indexing]], [[LSI]].

- Sparse matrix with each row for each word and each column for each document
    - Use [[tf-idf]] to weight each component
    - Do a [[singular value analysis]] on this matrix.
    - If we choose k largest singular values, we can [[embedding]] with the smallest error into k dimensions
            - [[Frobenius Norm.]]
    - Equivalent to learning a function for obtaining a word tf-idf vector from a document ID in an [[Autoencoder]]-like network with k hidden layers and 1 layer

---
This page is auto-translated from [/nishio/潜在意味解析](https://scrapbox.io/nishio/潜在意味解析) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
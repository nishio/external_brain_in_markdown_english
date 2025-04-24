---
title: "UMAP"
---

from [[BERTopic: Neural topic modeling with a class-based TF-IDF]]
UMAP
UMAP stands for Uniform Manifold Approximation and Projection and is a dimensionality reduction method for embedding high-dimensional data into low-dimensional space. [[BERTopic]] uses this UMAP to convert high-dimensional document embeddings into a low-dimensional space suitable for clustering.

UMAP has the following characteristics

1. nonlinear dimension reduction
UMAP is capable of nonlinear dimensionality reduction and preserves both the local and global structure of the data. This allows for a more faithful representation of the intrinsic structure of the data in a lower dimensional space.

2. high flexibility
UMAP has several hyperparameters, such as neighborhood graph construction methods and cost functions. By adjusting these parameters, you can obtain the optimal embedding according to the characteristics of your data.

3. scalability
UMAP works efficiently with large data sets. This is an important property when dealing with large numbers of documents, as in topic modeling.

4. probabilistic interpretation
The UMAP embedding has a probabilistic interpretation. This allows us to think of the distance on the embedding space as reflecting the similarity between the data points.

In BERTopic, documents are embedded into high-dimensional vectors in a language model such as BERT and then projected into a low-dimensional space using UMAP. Applying HDBSCAN on this low-dimensional space allows for efficient and effective clustering.

The non-linearity and scalability of UMAP allow BERTopic to extract meaningful topics even for large, noisy data sets. It is also possible to control the granularity of topics to some extent by adjusting the parameters of UMAP.

As described above, UMAP is an important preprocessing step in BERTopic, serving to convert high-dimensional document embeddings into a form suitable for clustering.

---
This page is auto-translated from [/nishio/UMAP](https://scrapbox.io/nishio/UMAP) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
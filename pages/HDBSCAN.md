---
title: "HDBSCAN"
---

from [[BERTopic: Neural topic modeling with a class-based TF-IDF]]
HDBSCAN
[[BERTopic]] uses the HDBSCAN algorithm to cluster documents on the embedding space. This is one of the key steps in BERTopic's topic modeling process.

HDBSCAN, which stands for Hierarchical Density-Based Spatial Clustering of Applications with Noise, is a density-based clustering algorithm. It has the following characteristics

1. can take into account differences in density
HDBSCAN allows clustering based on density differences. This automatically separates high-density and low-density areas to find more compact and meaningful clusters.

2. robust against noise
Points in low-density areas can be treated as noise, making them less susceptible to outliers. This is an important property in topic modeling to properly handle irrelevant documents.

3. no need to specify the number of clusters
Unlike many clustering methods, HDBSCAN does not require a pre-specified number of clusters. This is especially useful when the optimal number of topics is unknown.

4. [[hierarchical clustering]] is possible
HDBSCAN can capture the hierarchical structure of clusters. This may allow for topic granularity and the possibility of finding more detailed subtopics.

BERTopic uses this HDBSCAN algorithm to cluster documents in the embedding space, mapping each cluster to a single topic. This allows semantically related documents to be grouped into the same topic, resulting in a more interpretable topic model.
By taking advantage of the properties of HDBSCAN, BERTopic provides flexible topic extraction that is robust to noise and accounts for density differences.

---
This page is auto-translated from [/nishio/HDBSCAN](https://scrapbox.io/nishio/HDBSCAN) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
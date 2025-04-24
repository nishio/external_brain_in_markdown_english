---
title: "Talk to the City clustering"
---

2024-05-26
[[Talk to the City]] [[clustering]].
[source](https://github.com/AIObjectives/talk-to-the-city-reports/blob/main/scatter/pipeline/steps/clustering.py)

[[BERTopic]]
- Looks like this uses HDBSCAN and UMAP internally.
    - [[HDBSCAN]]
        - [HDBSCAN — scikit-learn 1.5.0 documentation](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.HDBSCAN.html)
        - > HDBSCAN - Hierarchical Density-Based Spatial Clustering of Applications with Noise. Performs [[DBSCAN]] over varying epsilon values and integrates the result to find a clustering that gives the best stability over epsilon. This allows HDBSCAN to find clusters of varying densities (unlike DBSCAN), and be more robust to parameter selection.
    - [[UMAP]]

---
This page is auto-translated from [/nishio/Talk to the Cityのクラスタリング](https://scrapbox.io/nishio/Talk to the Cityのクラスタリング) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
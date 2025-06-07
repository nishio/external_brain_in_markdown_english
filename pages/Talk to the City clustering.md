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

2025-06-06
<img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>Let me explain to you.
- Processing Flow
    - UMAP projects high-dimensional embedding to two dimensions
    - HDBSCAN + BERTopic to estimate "topic probability
    - Spectral Clustering determines the "final cluster" using the projected 2D coordinates
    - Save results to clusters.csv (output each argument with x-y position, probability, and cluster-id)


[[Spectral Clustering]] of the coordinate data after [[UMAP]] and the result of the document and the coordinate data after UMAP given to [[BERTopic]] which does [[HDBSCAN]] internally, are bundled and output with the cluster ID of the former and the probability of the latter. Isn't it possible that the clusters do not correspond to each other?
:

```
cluster_labels = spectral_model.fit_predict(umap_embeds)
result = topic_model.get_document_info(
    docs=docs,
    metadata={
        **metadatas,
        "x": umap_embeds[:, 0],
        "y": umap_embeds[:, 1],
    },
)
```


:

```
result = result[['arg-id', 'x', 'y', 'probability']]
result['cluster-id'] = cluster_labels
```

---
This page is auto-translated from [/nishio/Talk to the Cityのクラスタリング](https://scrapbox.io/nishio/Talk to the Cityのクラスタリング) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
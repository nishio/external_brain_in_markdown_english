---
title: "Clustering and Partitioning"
---

> K-Means has a few problems however. The first is that it isn’t a clustering algorithm, it is a partitioning algorithm. That is to say K-means doesn’t ‘find clusters’ it partitions your dataset into as many (assumed to be globular) chunks as you ask for by attempting to minimize intra-partition distances. --- [Comparing Python Clustering Algorithms — hdbscan 0.8.1 documentation](https://hdbscan.readthedocs.io/en/latest/comparing_clustering_algorithms.html)
There are several problems with K-Means: first, it is a partitioning algorithm, not a clustering algorithm. That is, rather than "finding clusters," K-means attempts to minimize the distances within partitions, dividing the dataset into the required number of (assumed to be spherical) chunks.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Okay, this is not the most common wording, but it's a nice distinction.
- K-Means ([[k-method]]) and [[Spectral Clustering]] are commonly called "[clustering
- However, the claim that these methods are not finding clusters, but are dividing the data set into chunks, so to speak, "[[partitioning]]"
- The [[DBSCAN]] paper also points out that "the definition of the concept of a cluster is vague to begin with.
        - [[Cluster Definition in DBSCAN]]
        - > Cluster: the largest set for which all points are density-connected to each other and from which any point in the cluster can be reached from any other point.

---
This page is auto-translated from [/nishio/クラスタリングとパーティショニング](https://scrapbox.io/nishio/クラスタリングとパーティショニング) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
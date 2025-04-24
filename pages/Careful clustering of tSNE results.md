---
title: "Careful clustering of tSNE results"
---

- I was given an interesting discussion regarding [Should UMAP results be clustered?
- [interpretation - Clustering on the output of t-SNE - Cross Validated](https://stats.stackexchange.com/questions/263539/clustering-on-the-output-of-t-sne)

- When applied to high-dimensional normal distributions that are inherently difficult to reduce to two dimensions, tSNE (and perhaps UMAP) can overreact to local density changes due to randomness, creating artifacts (non-existent clusters).
    - This problem is noticeable when experimenting with mathematically generated data.
- Real-world data often has "good features" such as a few scattered clusters of "high-density areas" surrounded by "low-density areas," so tSNE and UMAP, which visualize data based on distance from neighboring data points, can properly reduce dimensionality while preserving these features.
- On the other hand, if the data is used for a single block of high-dimensional data, some distortion will occur because the data is essentially two-dimensional and cannot be expressed in two dimensions. This can appear in the form of tearing apart a single cluster into multiple clusters or overstating density fluctuations that have no significant meaning, and this has a negative impact on the clustering at a later stage.
- Probably the real data is made up of several small, nicely separated clusters and one or two large, high-dimensional, hard-to-separate mud clusters, and "tSNE and kMeans" is the worst way to analyze these mud clusters because the density information is distorted, while DBSCAN systems are better because of their "focus on neighborhood" property similar to tSNE and UMAP. DBSCAN systems are better thanks to the "focus on the neighborhood" property similar to tSNE and UMAP (I wonder if SpectralClustering used by TTTC is the same?) However, in the heuristic of "using a high-density area as a seed and searching the neighborhood from there," there seems to be a possibility that the location of the seed may be wrong.
- In light of this, the method I tried in "[[Should UMAP results be clustered?]]" of separating the peripheral clusters from the central mudballs is still fine, but applying density estimation to the mudballs is clearly a bad idea. It would be better to give up visualization of the mudballs and cluster them on the higher dimensional space of the original data.
    - How to tackle [[high-dimensional mud pie]] will be a challenge for the future...

Especially when the original data is low-dimensional, [[tSNE]] and [[UMAP]] create artifacts
![image](https://gyazo.com/d4cd7ba17948672ce19213a871fe4130/thumb/1000)![image](https://gyazo.com/04d2c92a85dabbbcdc67321a1795706a/thumb/1000)
- [[string artifact]].

- [[high-dimensional mud pie]]
---
This page is auto-translated from [/nishio/tSNEの結果のクラスタリングは慎重に](https://scrapbox.io/nishio/tSNEの結果のクラスタリングは慎重に) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
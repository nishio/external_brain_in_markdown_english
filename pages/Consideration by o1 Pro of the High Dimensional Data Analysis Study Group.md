---
title: "Consideration by o1 Pro of the High Dimensional Data Analysis Study Group"
---

- Discussion by [[o1 Pro]] of [High-dimensional data analysis study group

This paper describes in detail the attempts to visualize and analyze high-dimensional data such as public opinion poll data and embedded vectors using nonlinear methods (UMAP, etc.). The paper demonstrates the possibility of revealing "complex structures" with nonlinear methods. However, in actual public opinion data, there are many lumpy structures without clear boundaries, such as "high-dimensional mud dumplings," rather than clear separations. Using DBSCAN/HDBSCAN for clustering allows a strategy of "extracting only the dense portions," but many data are considered "noise. Compare this to the KJ method, in which human beings rediscover and redefine relationships to group pieces of paper (data) with each other in a new perspective. Mechanical distance-based methods do not have this flexibility. In the future, new relationships will be generated using LLM and other methods, and a new dimension of clustering methods combining mechanical and human conception methods is expected.

point
- Technical evolution from PCA to UMAP: Effectiveness in capturing nonlinear manifold structure
- Unclear structure of real data (public opinion map) and missing value problem: UMAP visualization is sensitive to data characteristics
- Usefulness and limitations of density-based clustering (DBSCAN/HDBSCAN)
- Similarity/contrast with the KJ method: a method that avoids dogmatic wakugumi and rediscovers relationships by human hands.
- Possibility of rediscovering relationships through LLM, etc.: mechanical distance + human ideas → to new clustering concepts

New findings (brief)
- The "thin density areas" of high-dimensional data are not simply "noise," but can be interpreted as intermediate regions that unambiguously connect different clusters.
- Density extraction clustering" such as DBSCAN/HDBSCAN is closer to the KJ-like concept of "extracting only the dense parts first" than conventional "segmented clustering" (partitioning), but it still has the problem of treating a large amount of data as noise.
- Missing values and distance concepts on the embedding space can make the data appear to be more distinct clusters or strange structures than they really are.
- The strength of the human KJ method is that it forces "rediscovery of relationships" and finds connections that cannot be measured by physical distance. In the future, by using LLM to force machines to perform such "relationship creation," high-dimensional data analysis may gain more flexibility in KJ method thinking.
---
This page is auto-translated from [/nishio/高次元データ分析勉強会のo1 Proによる考察](https://scrapbox.io/nishio/高次元データ分析勉強会のo1 Proによる考察) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
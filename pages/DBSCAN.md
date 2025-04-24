---
title: "DBSCAN"
---

The hierarchical version of this is [[HDBSCAN]] (processing speed is slower, but parameter adjustment is easier)

Martin Ester, Hans-Peter Kriegel, Jörg Sander, and Xiaowei Xu. 1996. A density-based algorithm for discovering
clusters in large spatial databases with noise. In Proceedings of the 2nd ACM International Conference on Knowledge
Discovery and Data Mining (KDD). 226–231.
[A density-based algorithm for discovering clusters in large spatial databases with noise | Proceedings of the Second International Conference on Knowledge Discovery and Data Mining](https://dl.acm.org/doi/10.5555/3001460.3001507) [PDF](https://cdn.aaai.org/KDD/1996/KDD96-037.pdf)
<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>
This is the original paper on the DBSCAN (Density-Based Spatial Clustering of Applications with Noise) algorithm presented at the 1996 KDD conference. The main points are:.
1. features and benefits of DBSCAN: 1.
    - Density-based clustering method allows discovery of clusters of arbitrary shape
    - Noise (outliers) can be detected naturally
    - Fewer input parameters (only two: Eps, MinPts) and relatively easy parameter selection
    - Efficient for large spatial databases
- Algorithm Mechanism: 1.
    - [Introduced the concepts of density-reachability and density-connectivity.
        - ![image](https://gyazo.com/d228d417eb0cec4c9667370d240d6479/thumb/1000)
        - ![image](https://gyazo.com/e740ae1593f3ce3cd65ebbfd52675512/thumb/1000)
    - Define three types of points: core points, border points, and noise points
        - ![image](https://gyazo.com/76bef8d81d00751e6c47a594aa85d0d2/thumb/1000)
    - Efficiently search for neighboring points using R*-tree and other spatial indexes
3. performance evaluation
    - Comparison with CLARANS, the leading clustering method at the time
    - Excellent accuracy in finding clusters of arbitrary shape
    - Execution time is more than 100 times faster than CLARANS
- Parameter setting: 1.
    - MinPts is usually set to 4 (for 2D data)
    - Eps are determined interactively using a graph called k-dist plot
        - ![image](https://gyazo.com/1313cec66e1f5e7a0bd95d1721cb6ec9/thumb/1000)

This paper was an important foundational paper for DBSCAN and had a major impact on the field of density-based clustering; it received the SIGKDD Test of Time Award in 2014.
---
This page is auto-translated from [/nishio/DBSCAN](https://scrapbox.io/nishio/DBSCAN) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
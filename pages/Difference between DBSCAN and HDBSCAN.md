---
title: "Difference between DBSCAN and HDBSCAN"
---

Difference between [[DBSCAN]] and [HDBSCAN
- Simply put, HDBSCAN is a system that automatically adjusts the value of DBSCAN eps
- Experiment with real data to observe behavior

![image](https://gyazo.com/b33420c5a98cd016a3eebd26a505ddbe/thumb/1000) ![image](https://gyazo.com/656733acc1eb23cd794e535f551d0786/thumb/1000)
[https://pberba.github.io/stats/2020/01/17/hdbscan/](https://pberba.github.io/stats/2020/01/17/hdbscan/)
Illustration of eom([[Excess of Mass]]), the default cluster selection criteria for HDBSCAN


2024-11-14
![image](https://gyazo.com/ff7c969a58a1b63a88fc375355dab761/thumb/1000)
- lower left
    - HDBSCAN recognizes the lower left "clearly separated cluster" as a whole cluster, regardless of the parameters.
    - DBSCAN ignores the end part as noise, gradually decreasing in size as the parameters change, and finally judging all of it as noise.
- right
    - There's not much difference in behavior, but HDBSCAN's are more likely to judge the surrounding noise as part of the cluster and get involved.

[DBSCAN — scikit-learn 1.5.2 documentation](https://scikit-learn.org/1.5/modules/generated/sklearn.cluster.DBSCAN.html)
[[DBSCAN Revisited, Revisited: Why and How You Should (Still) Use DBSCAN]]

[HDBSCAN — scikit-learn 1.5.2 documentation](https://scikit-learn.org/1.5/modules/generated/sklearn.cluster.HDBSCAN.html)
[https://note.com/navy_azalea/n/na859d7ab6ab3](https://note.com/navy_azalea/n/na859d7ab6ab3)
- [[Mutual reach]]

[SpectralClustering — scikit-learn 1.5.2 documentation](https://scikit-learn.org/1.5/modules/generated/sklearn.cluster.SpectralClustering.html)

---
This page is auto-translated from [/nishio/DBSCANとHDBSCANの違い](https://scrapbox.io/nishio/DBSCANとHDBSCANの違い) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
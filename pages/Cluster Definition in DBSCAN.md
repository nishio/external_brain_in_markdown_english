---
title: "Cluster Definition in DBSCAN"
---

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
In [[DBSCAN]], clusters are defined as follows
- [Core Point: A point is a core point if at least minPts of points exist within a radius of epsilon centered at that point.
- [Directly Reachable: If point p is a core point and point q is within distance ε of p, then q is considered directly reachable from p.
- Reachable: If there is a sequence of consecutive directly reachable points from point p to point q, then q is considered reachable from p.
- [Density-Connected: Points p and q are density-connected if they are reachable from each other via some point o.

Based on these concepts, DBSCAN defines clusters as follows
- Cluster: the largest set of points for which all points are density-connected to each other and from which any point in the cluster can be reached from any other point.
- Noise point: not belonging to any cluster.

Thus, DBSCAN defines clusters based on data density and identifies noise points.


---
This page is auto-translated from [/nishio/DBSCANにおけるクラスタの定義](https://scrapbox.io/nishio/DBSCANにおけるクラスタの定義) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
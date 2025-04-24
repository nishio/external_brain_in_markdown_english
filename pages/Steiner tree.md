---
title: "Steiner tree"
---

> A Steiner tree is an undirected graph G=(V,E) consisting of a set of edges E and a set of nodes V. Given a subset T of V, a Steiner tree is a tree containing all the nodes in T. From the definition, it is clear that a Steiner tree is a [[universal tree]] when T=V.

    - The [[Minimum Steiner Tree]] problem is a loosening of the [[minimum area tree]] problem so that not all vertices need to be connected.
- [[Dreyfus-Wagner]]
    - Time complexity O(n 3^t + n^2 2^t + n^3)
    - Implementation [Spaghetti Source - Smallest Steiner Tree](http://www.prefield.com/algorithm/dp/steiner_tree.html)
    - The limit is about the required vertex t = 11
- When there are many required vertices and few optional vertices, there is a move to search all optional vertex selections
    - [[PAST1L]]

---
This page is auto-translated from [/nishio/シュタイナー木](https://scrapbox.io/nishio/シュタイナー木) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
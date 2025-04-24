---
title: "Kruskal method"
---

- Algorithm for finding the [[minimum area tree]] of an undirected connected graph
- O(E log E)
- Add the cost of the sides from the cheapest to the least expensive to avoid creating a closed channel.
    - This closed path can be determined in almost constant time by using [UnionFind
    - O(E log E) where the edges are sorted by cost.
        - O(E) if sorted or [[linear time sort]] if possible

- [Minimum Global Tree (Kruskal Method and UnionFind) - Algorithm Workshop](https://dai1741.github.io/maximum-algo-2012/docs/minimum-spanning-tree/)
- [Kruskal Act - Wikipedia](https://ja.wikipedia.org/wiki/%E3%82%AF%E3%83%A9%E3%82%B9%E3%82%AB%E3%83%AB%E6%B3%95)

---
This page is auto-translated from [/nishio/クラスカル法](https://scrapbox.io/nishio/クラスカル法) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
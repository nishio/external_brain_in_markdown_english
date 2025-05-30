---
title: "least common ancestor"
---

[[Lowest Common Ancestor]]([[LCA]])
Given vertices a and b of a tree, the deepest of both ancestral vertices

How to get it
- Doubling when pointers to parents are given.
    - pretreatment
        - Create a pointer from each vertex to its children
        - Find the depth of each vertex in DFS
        - [[doubling]] the pointer to the parent to get 2^i vertices up (O(NlogN))
    - query
        - Get the depth of the given 2 vertices
        - Select some upper vertices on the deeper side and align the heights.
        - Find the smallest n for which the n upper parents are the same by a binary search.
- remarks
    - The process of getting n upper parents is O(logN), but we can make the whole process O((logN)^2)→O(logN) if we try from the top when we do a binary search
        - I thought I could do without doing this since it is at most 20 times faster, but if I didn't do this, it would have been a TLE.
            - [[AOJ GRL_5_C]] [https://onlinejudge.u-aizu.ac.jp/problems/GRL_5_C](https://onlinejudge.u-aizu.ac.jp/problems/GRL_5_C)


---

[Algorithm for finding the Lowest Common Ancestor (LCA) of a tree by doubling | Algorithm Logic](https://algo-logic.info/lca/)
- Patterns given a graph and parent vertex

[[LCA]]  [[doubling]]

- [[Euler Tour]]   [[sparse table]]
[https://ikatakos.com/pot/programming_algorithm/graph_theory/lowest_common_ancestor](https://ikatakos.com/pot/programming_algorithm/graph_theory/lowest_common_ancestor)


[[ABC014D]]

---
This page is auto-translated from [/nishio/最小共通祖先](https://scrapbox.io/nishio/最小共通祖先) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
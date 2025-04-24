---
title: "UnionFind"
---

Fast merging of sets and checking for common sets [[data structure]].
It can be viewed as adding an edge to the graph and checking whether two vertices are connected or not is fast.

For a relation between N objects, if it can be decomposed into iffs, it can be described as a graph edge
- For example, "x beats y" when there is a target that is either goo or chokiper is equivalent to adding 3 edges to the 3N vertex set because it can be decomposed into 3 iff's such as "x is goo iff y is chokiper".
- The connected component corresponds to a solution that satisfies the condition
- If not iff -> [[2-SAT]].

[https://judge.yosupo.jp/submission/12685](https://judge.yosupo.jp/submission/12685)

    - [[prime set data structure]]  [Wikipedia](https://ja.wikipedia.org/wiki/%E7%B4%A0%E9%9B%86%E5%90%88%E3%83%87%E3%83%BC%E3%82%BF%E6%A7%8B%E9%80%A0)
- [[Disjoint Set Union]] ([[DSU]])
- [[Union-Find]]

---
This page is auto-translated from [/nishio/UnionFind](https://scrapbox.io/nishio/UnionFind) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
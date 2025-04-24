---
title: "Sparse Table"
---

Given a sequence of static values of length N, a data structure where the preprocessing O(NlogN) allows operations on the upper interval of the sequence to be computed in O(1)

The operations that can be used are concrete, such as min, argmin is also acceptable
    - [[crossing half a bundle (e.g. of swords)]]
        - [[associative law]] : $(a * b) * c = a * (b * c)$
        - [[commutative law]] : $a * b = b * a$
        - [[power]] : $a * a = a$

Construction O(N log N)
- Calculate the min of an interval of length 2 beki from each point
- An interval of length 2^k can be calculated in constant order from two intervals of half length, so DP from the smaller one.

query
- Cover the query interval with two calculated intervals of maximum length smaller than the length of the query interval
- For example, cover with 1-4 and 4-7 for sections 1-7.
- The minimum value of the query interval is the minimum value in either of the two intervals

Use [[segment tree]] when columns are updated
    - [[Sparse Tables and Segment Trees]]

For finding the [[least common ancestor]] of a tree by [[Euler Tour]] +[[Range Minimum Query]].
- [Minimum Common Ancestor [ikatako takotsubo]](https://ikatakos.com/pot/programming_algorithm/graph_theory/lowest_common_ancestor)

[Sparse-Table | Luzhiled's memo](https://ei1333.github.io/luzhiled/snippets/structure/sparse-table.html)

Can be extended to two dimensions
- [Summary of Sparse Table issues in competitive programming - Hamayan Hamayan](https://www.hamayanhamayan.com/entry/2018/01/03/035508)
- [[2D Sparse Table]]
    - [[2D Range Minimum Query]]
        - [2D Range Minimum Query in O(1) - Codeforces](http://codeforces.com/blog/entry/45485)

- [[sparse table]]

---
This page is auto-translated from [/nishio/Sparse Table](https://scrapbox.io/nishio/Sparse Table) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
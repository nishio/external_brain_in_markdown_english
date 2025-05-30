---
title: "Maximize the sum ratio"
---

Let S be K positive sequences Ai, Bi of length N. We want to maximize the [[Ratio]] of the sum of each of AB

$\argmax_S { \sum_{i\in S} B_i \over \sum_{i\in S} A_i }$

Instead of directly maximizing the ratio of sums, there is a solution method that makes it a problem of determining whether the ratio of sums is greater than or equal to X, and then bisectively searching for X
- ${\sum B_i \over \sum A_i} \ge X$
- $\sum B_i \ge X \sum A_i$
- $\sum B_i - X \sum A_i \ge 0$
- $\sum (B_i - X A_i) \ge 0$
If there exists an S satisfying the condition, then the K selections from which $B_i - X A_i$ is larger satisfy the condition.
Therefore, this decision problem can be solved by O(NlogN).

A [[dichotomous search]] of this X will find the largest X for which S satisfies the condition. This is the maximum value of X.

- [[Maximize concentration]]

---
This page is auto-translated from [/nishio/和の比率の最大化](https://scrapbox.io/nishio/和の比率の最大化) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
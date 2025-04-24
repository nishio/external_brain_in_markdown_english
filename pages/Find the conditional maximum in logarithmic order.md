---
title: "Find the conditional maximum in logarithmic order"
---

Given two sequences Ai, Bi, we want to find the largest Ai for which Bi does not exceed x.
If it is a single shot, it can be found in linear order, but since it is repeated with different x, we want to preprocess it to logarithmic order.

Sort (Ai, Bi) in lexicographic order and remove j such that Bj>Bi and Aj<=Ai. Because they will never be a solution.
![image](https://gyazo.com/e98e4afca708b1d6ecc8f4325e03405f/thumb/1000)
For the columns removed, find the largest i for which Bi does not exceed x in a binary search.

- [[anthology]] p.149

---
This page is auto-translated from [/nishio/条件付き最大値を対数オーダーで求める](https://scrapbox.io/nishio/条件付き最大値を対数オーダーで求める) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
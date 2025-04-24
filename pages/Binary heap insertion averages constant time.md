---
title: "Binary heap insertion averages constant time"
---

- Insert into [binary heap
- After adding to the leaf, it needs to swap with the parent until the constraints are met
- At worst, tree height O(logN)
- But since there are 2^n vertices of depth n?
    - The probability of having to replace a parent.
    - (Every time you go forward?) Because it will be 1/2,
    - Is it a constant if we find the mean?
- A little dubious.
- > The average cost of inserting n elements into an initially empty heap is analyzed, under the assumption that the n! orders in which the n elements can be inserted are equally likely. It is proved that this average, expressed in number of exchanges per insertion, is bounded by a constant about 1.7645.
    - [https://www.sciencedirect.com/science/article/abs/pii/0196677485900288](https://www.sciencedirect.com/science/article/abs/pii/0196677485900288)

- Merge one element into [binary heap
- Since the probability of needing to carry forward for the same reason is 1/2, the average number of carry forward operations is of constant order

---
This page is auto-translated from [/nishio/二分ヒープの挿入が平均定数時間](https://scrapbox.io/nishio/二分ヒープの挿入が平均定数時間) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "segment tree"
---

Given a sequence of a fixed number of values, operations can be performed on that interval in logarithmic time [[data structure]].
- Occurs quite frequently in AtCoder
- [Data Structures in Programming Contests](https://www.slideshare.net/iwiwi/ss-3578491) [[Takuya Akiba]] p.33~

- Update value O(logN)
- Operation on interval O(logN)
    - For example, "sum of the interval" for addition, and "max of the interval" for max.
    - See [[Delayed propagation segment tree]] for possible operations

It is not possible to delete elements, but there is no harm in doing so, since the sum can be updated with 0 instead of deletion, and the minimum value can be updated with a sufficiently large number.

An efficient way to find the minimum value is [[heapq]], but since this one is random access and updates are not straightforward, the approach is to achieve deletion by skipping over invalid values.

My implementation
[https://judge.yosupo.jp/submission/12659](https://judge.yosupo.jp/submission/12659)
- [Static RMQ](https://judge.yosupo.jp/problem/staticrmq) so we're building it in batches.
- [Point Add Range Sum](https://judge.yosupo.jp/problem/point_add_range_sum)
    - [Submitted](https://judge.yosupo.jp/submission/12646) [[Fennic tree]] implementation
- → Later make a version with segmented trees.

---
This page is auto-translated from [/nishio/セグメント木](https://scrapbox.io/nishio/セグメント木) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
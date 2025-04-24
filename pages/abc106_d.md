---
title: "abc106_d"
---

[https://atcoder.jp/contests/abc106/tasks/abc106_d](https://atcoder.jp/contests/abc106/tasks/abc106_d)
- Thoughts.
    - Given 200,000 intervals, answer the number of items that are completely contained in the interval given 100,000 times.
    - I want to do some kind of preprocessing and answer on the order of a constant or logarithm.
    - Difficult to think in general terms, so check the constraints.
        - N is 500, so we can reserve a table for a squared order.
        - If only there was a data structure that could increment a two-dimensional rectangular interval...
            - The one that looks like a twin-pair segmented tree turned two-dimensional.
- Official Explanation
    - O(N) for each query, but N is small enough to make it.
        - I noticed that N is small, but I was only thinking about the spatial computational complexity, which also loosens up "on the order of a constant or logarithm".
    - I had imagined a dual segment tree with range increment point acquisition in the data structure, but it was more natural to think in terms of point increment range summation.
    - If you've thought that far, you can just [[cumulative sum]] the range sum O(N^2) to O(N)
        - It would be faster to use [[two-dimensional cumulative story]], but that's not what we're looking for.

---
This page is auto-translated from [/nishio/abc106_d](https://scrapbox.io/nishio/abc106_d) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
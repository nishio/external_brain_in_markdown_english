---
title: "Sparse Tables and Segment Trees"
---

- [[sparse table]] Construct O(NlogN), range query O(1), target not updatable
- [[segment tree]] update O(logN), range query O(logN)

Segment trees can be constructed on the same order as sparse tables by updating each value
- I feel like I can make it O(N) by initializing them all together.

Segment tree range queries are certainly slower than sparse tables
- but after doing it N times, it finally catches up to the same level of order as the sparse table construction, so much so that
- If the query is Q times, there is no advantage to use sparse table only when the time constraint is OK for O(Q) and NG for O(QlogN).
    - It's hard to create that kind of restriction in a contest where you can use a variety of languages.
---
This page is auto-translated from [/nishio/スパーステーブルとセグメント木](https://scrapbox.io/nishio/スパーステーブルとセグメント木) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
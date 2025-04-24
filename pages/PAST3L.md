---
title: "PAST3L"
---

[L](https://atcoder.jp/contests/past202005-open/tasks/past202005_l) Up to 100,000 different numbers in up to 100,000 columns, up to 300,000 numbers. 300,000 queries to "take the first one maximum value" or "take the first two maximum values". query to "take the largest value of the first one" or "take the largest value of the first two" 300,000 times.

As a result of studying [[heapq]] in [[ABC170]], I felt I could solve it.

Use "first one" and "first two" heapq.
Need a way to skip reading it because it will remain on the other side when taken from one side.
For each column, prepare two pointers that point to the queued item, and rewrite the number taken to None so that it can be skipped.

AC [https://atcoder.jp/contests/past202005-open/submissions/14404930](https://atcoder.jp/contests/past202005-open/submissions/14404930)

---
This page is auto-translated from [/nishio/PAST3L](https://scrapbox.io/nishio/PAST3L) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
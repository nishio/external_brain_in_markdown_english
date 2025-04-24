---
title: "number of events (e.g. accidents, crimes, meetings, housing starts, hits on a web page)"
---

An inversion of a sequence in computer science and discrete mathematics is a pair of terms in that sequence such that the components of those terms are out of their natural order.
$\mathrm{inv}(A)=\#\{(A_{i},A_{j})\mid i<j{\,\,\mathrm{ and }\,\,}A_{i}>A_{j}\}$

The number of overturns in the combined column x+y is obtained from the respective number of overturns f and the frequency table c [[ACLPC L]] [[PAST4K]].
- $f(x + y) = f(x) + f(y) + \sum_i\sum_j c(x, i)c(y, j)[i > j]$

- [[Fennic tree]] and obtained by O(NlogN)
python

```
init(N)
inv = 0
for a in seqs[i]:
    bit_add(a, 1)
    inv += bit_sum(N) - bit_sum(a)
```



---
This page is auto-translated from [/nishio/転倒数](https://scrapbox.io/nishio/転倒数) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
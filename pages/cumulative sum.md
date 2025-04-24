---
title: "cumulative sum"
---

I want to take the sum of successive parts of a sequence of numbers.
- Order of length of partial rows when taken naively
- By taking the story from the beginning in advance, O(1) requires
    - Takes O(N) to prepare.
    - Benefit from using it when repeating about N times.
python

```
from itertools import accumulate, chain
XS = [1, 2, 3, 4, 5]
acc = list(chain([0], accumulate(XS)))
print(acc)  # => [0, 1, 3, 6, 10, 15]
assert acc[4] - acc[3] == XS[3]
assert acc[4] - acc[1] == sum(XS[1:4]) 
```


The former is significantly faster than the latter in terms of initialization with the guard, but it's not a significant difference considering the frequency of initialization.
python

```
In []: XS = range(1000000)

In []: %timeit list(chain([0], accumulate(XS)))
78.5 ms ± 648 µs per loop (mean ± std. dev. of 7 runs, 10 loops each)

In []: %timeit [0] + list(accumulate(XS))
89.2 ms ± 1.3 ms per loop (mean ± std. dev. of 7 runs, 10 loops each)
```


Dynamic generation of cumulative sums during DP, etc.
    - [[DP with cumulative sum]]


One-dimensional [[zeta transformation]].
[https://qiita.com/convexineq/items/afc84dfb9ee4ec4a67d5](https://qiita.com/convexineq/items/afc84dfb9ee4ec4a67d5)

---
This page is auto-translated from [/nishio/累積和](https://scrapbox.io/nishio/累積和) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
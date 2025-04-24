---
title: "Python list v.s. set"
---

Compared to append to list, add to set is about 70ns slower
- Cost of computing hash values, etc.
- This is a C-world cost, so it's hard to shrink, even with PyPy or something like that.
    - As a result, as occurred in [[ABC176]], "it is faster to make the loop spin than to make it unique with set.
python

```
In [77]: %%timeit
    ...: xs = []
    ...: xs.append(1)
    ...: 
71.9 ns ± 1.01 ns per loop (mean ± std. dev. of 7 runs, 10000000 loops each)

In [78]: %%timeit
    ...: xs = set()
    ...: xs.add(1)
    ...: 
141 ns ± 0.457 ns per loop (mean ± std. dev. of 7 runs, 10000000 loops each)
```


---
This page is auto-translated from [/nishio/Python list v.s. set](https://scrapbox.io/nishio/Python list v.s. set) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "NUMPY subscript access is slow."
---

For algorithms that require repeated random accesses with subscripts, it is faster to keep the list than to use numpy.array.
python

```
In [71]: %%timeit
    ...: xs = np.zeros(100)
    ...: xs[0]
    ...: 
696 ns ± 4.94 ns per loop (mean ± std. dev. of 7 runs, 1000000 loops each)

In [72]: %%timeit
    ...: xs = [0] * 100
    ...: xs[0]
    ...: 
416 ns ± 3.79 ns per loop (mean ± std. dev. of 7 runs, 1000000 loops each)
```

---
This page is auto-translated from [/nishio/numpyの添え字アクセスは遅い](https://scrapbox.io/nishio/numpyの添え字アクセスは遅い) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
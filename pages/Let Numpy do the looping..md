---
title: "Let Numpy do the looping."
---

When using Numpy, whether the loop is done on the Numpy side or the Python side greatly affects the speed.

sum(xs) v.s. xs.sum(): xs.sum() is 178 times faster
- In sum(xs), Python side considers np.array as just a generic iterable and sums it.
- In xs.sum(), the Numpy side understands that it is np.array and sums
- In the latter case, the entire cost of turning the value into a PyFloat object is eliminated.
python

```
In [3]: xs = np.arange(1000_000)

In [4]: %timeit sum(xs)
80.5 ms ± 210 µs per loop (mean ± std. dev. of 7 runs, 10 loops each)

In [5]: %timeit xs.sum()
448 µs ± 4.18 µs per loop (mean ± std. dev. of 7 runs, 1000 loops each)
```


Increment by subscript access vs. broadcast, the latter is 205 times faster
- (The latter is a bit unfair since it is a local variable for benchmarking reasons.)
- [Broadcasting — NumPy v1.19 Manual](https://numpy.org/doc/stable/user/basics.broadcasting.html)
python

```
In [7]: %%timeit
   ...: for i in range(1000_000):
   ...:     xs[i] += 1
   ...: 
284 ms ± 1.88 ms per loop (mean ± std. dev. of 7 runs, 1 loop each)

In [11]: %%timeit
    ...: xs = np.arange(1000_000)
    ...: xs += 1
    ...: 
1.38 ms ± 25.3 µs per loop (mean ± std. dev. of 7 runs, 1000 loops each)
```


---
This page is auto-translated from [/nishio/ループをNumpyに任せる](https://scrapbox.io/nishio/ループをNumpyに任せる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
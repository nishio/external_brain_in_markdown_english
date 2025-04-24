---
title: "Fast long integers"
---

Python's long integers are surprisingly fast, so if you want to add a value of 10^100 at most 1000 times, it's faster to calculate it as it is without removing the remainder each time.
python

```
In [27]: %%timeit
    ...: x = int("7" * 100)
    ...: for i in range(1000):
    ...:     x += x
    ...: 
71.3 µs ± 624 ns per loop (mean ± std. dev. of 7 runs, 10000 loops each)

In [28]: %%timeit
    ...: x = int("7" * 100)
    ...: for i in range(1000):
    ...:     x += x
    ...:     x %= 1000000007
    ...: 
104 µs ± 890 ns per loop (mean ± std. dev. of 7 runs, 10000 loops each)
```


- In [[ABC177]], the code that computes without taking the remainder each time and takes the remainder at the end was the fastest in the PyPy3 submission
    - This problem was 10^9 times 10^6 additive multiplications at the highest, and the maximum could fit into about 10^30.

---
This page is auto-translated from [/nishio/長整数が速い](https://scrapbox.io/nishio/長整数が速い) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Cumulative product from left to right"
---

I want to take the product of N numbers minus one [[obsolete rule prohibiting match-ups between wrestlers from the same group of stables]].
- Just take the cumulative product from the left and the cumulative product from the right and multiply them together with one gap.
- If we do it simply, O(N^2) becomes O(N).
- Simple solution for N=3000 takes 3 seconds, but this method takes 2 milliseconds.
python

```
def one_out_product_fast(xs):
    N = len(xs)
    ret = [1] * N
    prod = 1
    for i in range(N):
        ret[i] = prod
        prod *= xs[i]
        prod %= MOD
    prod = 1
    for i in range(N - 1, -1, -1):
        ret[i] *= prod
        ret[i] %= MOD
        prod *= xs[i]
        prod %= MOD
    return ret


def bluteforce(xs):
    N = len(xs)
    ret = [1] * N
    for i in range(N):
        for j in range(N):
            if i == j:
                continue
            ret[i] *= xs[j]
            ret[i] %= MOD

    return ret
```

:

```
N=3000
%timeit one_out_product_fast(xs)
2.14 ms ± 55 µs per loop (mean ± std. dev. of 7 runs, 100 loops each)
%timeit bluteforce(xs)
2.98 s ± 18.2 ms per loop (mean ± std. dev. of 7 runs, 1 loop each)
```

[https://github.com/nishio/atcoder/blob/master/memo/one_out_product.py](https://github.com/nishio/atcoder/blob/master/memo/one_out_product.py)

---
This page is auto-translated from [/nishio/左右から累積積](https://scrapbox.io/nishio/左右から累積積) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
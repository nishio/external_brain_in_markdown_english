---
title: "DP with cumulative sum"
---

- [[dynamic programming]] while [[cumulative sum]].
[[ABC179D]]

Dynamic generation of cumulative sums during DP, etc.
- [[ABC179]]D
python

```
def accum_generation(N):
    """
    >>> accum_generation(10)
    [1, 0, 1, 1, 1, 2, 2, 3, 4, 5]
    """
    value = [0] * (N + 10)
    accum = [0] * (N + 10)
    value[0] = 1
    accum[0] = 1
    for pos in range(1, N):
        ret = (accum[pos - 2] - accum[pos - 4])
        value[pos] = ret
        accum[pos] = accum[pos - 1] + ret

    return value[:N]
```


---
This page is auto-translated from [/nishio/累積和しながらDP](https://scrapbox.io/nishio/累積和しながらDP) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Extended Euclidean reciprocal division"
---

- Using [[Euclid's reciprocal division]], we can obtain the solution x,y of mx + ny = gcd(m, n)
In particular, mx+ny=1 when m and n are prime to each other, and this form is often used

python

```
def extended_euclidean(a, b, test=False):
    """
    Extended Euclidean algorithm
    Given a, b, solve:
    ax + by = gcd(a, b)
    Returns x, y, gcd(a, b)

    Other form, for a prime b:
    ax mod b = gcd(a, b) = 1

    >>> extended_euclidean(3, 5, test=True)
    3 * 2 + 5 * -1 = 1 True
    >>> extended_euclidean(240, 46, test=True)
    240 * -9 + 46 * 47 = 2 True
    """
    init_a = a
    init_b = b
    s, u, v, w = 1, 0, 0, 1
    while b:
        q, r = divmod(a, b)
        a, b = b, r
        s, u, v, w = v, w, s - q * v, u - q * w

    if test:    
        print(f"{init_a} * {s} + {init_b} * {u} = {a}", init_a * s + init_b * u == a)
    else:
        return s, u, a
```



---
This page is auto-translated from [/nishio/拡張ユークリッド互除法](https://scrapbox.io/nishio/拡張ユークリッド互除法) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
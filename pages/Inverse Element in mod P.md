---
title: "Inverse Element in mod P"
---

Fermat's minor theorem
- $a^{p-1}\equiv 1{\pmod {p}}$
by transforming
- $a \times a^{p-2}\equiv 1{\pmod {p}}$
therefore
- $a^{-1} \equiv a^{p-2} {\pmod {p}}$

Python: `pow(a, p - 2, p)`
Can `pow(a, -1, p)` straightforwardly from Python 3.8

Fermat's minor theorem requires P to be prime
- Use [[Extended Euclidean reciprocal division]] for non-prime numbers [[P is not prime mod P]]
- In this case, a and p need only be prime to each other
python

```
def mod_inverse_ee(a, m):
    """
     Solve ax mod m = 1 with extended euclidean.
     x = a^-1.
     """
    x, y, g = extended_euclidean(a, m)
    assert g == 1
    return x % m
[Division by the remainder group] 
```



The inverse in modulo p of >n is from [Fermat's minor theorem
>  pow(n, p-2, p)
>  , which is obtained by The computational quantity is O(logp). It is often used with [[binomial coefficient]].
[https://qiita.com/Kentaro_okumura/items/5b95b767a2e691cd5482](https://qiita.com/Kentaro_okumura/items/5b95b767a2e691cd5482)

---
This page is auto-translated from [/nishio/mod Pでの逆元](https://scrapbox.io/nishio/mod Pでの逆元) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
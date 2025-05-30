---
title: "Chinese remainder theorem"
---

[[CRT]] Chinese Remainder Theorem

For mutually prime [$ m, n
$x \equiv a \pmod{m}, x \equiv b \pmod{n}$
time,
$x \equiv c \pmod{mn}$
There exists only one $0 \le c < ab$ that satisfies

Existence of a solution
- c can be obtained by [Extended Euclidean reciprocal division
python

```
def crt(a, m, b, n):
    """
    Find x s.t. x % m == a and x % n == b
    >>> crt(2, 3, 1, 5)
    11
    >>> crt(1, 4, 3, 6)
    9
    """
    x, y, g = extended_euclidean(m, n)
    if g == 1:
        return (b * m * x + a * n * y) % (m * n)
    s = (b - a) // g
    return (a + s * m * x) % (m * n // g)
```

- [src](https://github.com/nishio/atcoder/blob/master/libs/crt.py)
- Find $mx + ny = 1$ s $x, y$ by extended Euclidean reciprocal division
- $mx \pmod{n} = 1, ny \pmod{m} = 1$, so $bmx + any$ satisfies the condition

Click here for solution uniqueness, etc.
- [Chinese Remainder Theorem (CRT) and a summary of problems that use it - Qiita](https://qiita.com/drken/items/ae02240cd1f8edfc86fd)
---
This page is auto-translated from [/nishio/中国剰余定理](https://scrapbox.io/nishio/中国剰余定理) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
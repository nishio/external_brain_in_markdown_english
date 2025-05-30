---
title: "eq7-proof"
---

from  [[binomial coefficient formula]]
- eq7-proof
    - Consider a formal power series F such that $[x^k]F = \sum_{i=0}^k \binom{n+1}{i}\binom{m-i}{k - i}$
    - $\displaystyle F = \sum _ {k=0}^{\infty} \sum_{i=0}^{k} {n+i \choose i}{m-i \choose k-i} x^{k}$
    - When $k < i$ $\binom{m-i}{k-i} = 0$, so $\sum_{i=0}^{k}$ can be [$ \sum_{i=0}^{\infty}
    - $\displaystyle F = \sum _ {k=0}^{\infty} \sum _ {i=0}^{\infty} {n+i \choose i}{m-i \choose k-i} x^{k}$
    - $\displaystyle F = \sum_{i=0}^{\infty} \sum_{k=0}^{\infty} {n+i \choose i}{m-i \choose k-i} x^{k}$ ...  [[Change the order of addition]]
    - $\displaystyle F = \sum_{i=0}^{\infty}\left({n+i \choose i} \sum_{k=0}^{\infty} {m-i \choose k-i} x^{k}\right)$ ... We can dwell on the coefficients independent of k, and then use
    - $k < i$ as $\binom{m-i}{k-i} = 0$ so [$ j=k - i \quad (j > 0)
    - $\displaystyle F = \sum_{i=0}^{\infty}\left({n+i \choose i} \sum_{j=0}^{\infty} {m-i \choose j} x^{j}x^i\right)$

    - $\displaystyle F = \sum_{i=0}^{\infty}\left({n+i \choose i} (1+x)^{m-i} x^i\right)$ ...  [[binomial theorem]]

    - $\displaystyle F = \sum_{i=0}^{\infty}\left({n+i \choose i} (1+x)^m(1+x)^{-i} x^i\right)$
    - $\displaystyle F = (1+x)^m \sum_{i=0}^{\infty}\left({n+i \choose i} \left(\frac{x}{1+x}\right)^i \right)$ ... We can lump together the coefficients independent of i
    - $\displaystyle F = (1+x)^m \sum_{i=0}^{\infty}\left({i+n \choose n} \left(\frac{x}{1+x}\right)^i \right)$ ... by eq4-3
    - $\displaystyle F = (1+x)^m / \left(1 - \frac{x}{1+x}\right)^{n+1} $ ...  [[negative binomial theorem]]
    - $\displaystyle F = (1+x)^m / \left(\frac{1}{1+x}\right)^{n+1} $

    - $\displaystyle F = (1+x)^m (1+x)^{n+1} $

    - $\displaystyle F = (1+x)^{m+n+1} $
    - $\displaystyle F = \sum_{k=0}^\infty \binom{m+n+1}{k} x^k$...  [[binomial theorem]]
    - $[x^k]F = \binom{m+n+1}{k}$

---
This page is auto-translated from [/nishio/eq7-proof](https://scrapbox.io/nishio/eq7-proof) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
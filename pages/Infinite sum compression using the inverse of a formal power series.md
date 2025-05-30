---
title: "Infinite sum compression using the inverse of a formal power series"
---

- Infinite sum compression using the inverse of [formal power series
- [Polynomial and Formal Power Series (2) Derivation of Solutions by Expression Transformation | maspy's HP [https://maspypy.com/%e5%a4%9a%e9%a0%85%e5%bc%8f%e3%83%bb%e5%bd%a2%e5%bc%8f%e7%9a%84%e3%81%b9%e3](https://maspypy.com/%e5%a4%9a%e9%a0%85%e5%bc%8f%e3%83%bb%e5%bd%a2%e5%bc%8f%e7%9a%84%e3%81%b9%e3) I have paraphrased a passage from [[%81%8d%e7%b4%9a%e6%95%b0%ef%bc%88%ef%bc%92%ef%bc%89%e5%bc%8f%e5%a4%89%e5%bd%a2%e3%81%ab%e3%82%88%e3%82%8b%e8%a7%a3%e6%b3%95]] to the point where I can to a point where I can understand it.

- inverse element
    - $A = \sum_{n=0}^\infty x^n$
    - $B = 1-x$
    - At this time [$ A \times B = 1
        - $A = 1 +  x + x^2 + \ldots$ (1)
        - $xA =  x + x^2 + \ldots$ (2)
        - $(1-x)A = 1$ (1) - (2)
        - Common techniques for calculating sums of sequences of equal ratios
    - Generally when F is a formal power series without a constant term such that $[x^0]F = 0$,
        - $(1-F) \times (\sum_{n=0}^\infty F^n) = 1$
        - The proof requires defining a phase in the formal power ring and defining convergence

Count up the number of ways to express N as a sum of positive integers. However, distinguish between different orders of sums.
- $F = \sum_{n=1}^\infty x^n$,[$ G = \sum_{n=0}^\infty F^n
- $[x^n]G$ is the answer
- Replace the infinite sum of G with the inverse original
    - $G = \sum_{n=0}^\infty F^n = \frac{1}{1 - F}$
- The infinite sum of F is also replaced by the inverse element
    - $F = \sum_{n=1}^\infty x^n = \sum_{n=0}^\infty x^{n+1} = x\sum_{n=0}^\infty x^n = \frac{x}{1-x}$
- Substitute F for G
    - $G = \frac{1}{1 - F} = \frac{1}{1-\frac{x}{1-x}} = (1-x) \frac{1}{1-2x}$
- where the $2x$ part is a formal power series, so we can return to infinite sums, which we will call J
- $J = \frac{1}{1-2x} = \sum_{n=0}^\infty (2x)^n$
    - $[x^n]J = 2^n$
    - From here $[x^n] G = [x^n](1-x)J = [x^n]J - [x^{n-1}]J = 2^n - 2^{n-1} = 2^{n-1}$

---
This page is auto-translated from [/nishio/形式的べき級数の逆元を使った無限和圧縮](https://scrapbox.io/nishio/形式的べき級数の逆元を使った無限和圧縮) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
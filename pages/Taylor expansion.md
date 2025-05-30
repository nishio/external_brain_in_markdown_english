---
title: "Taylor expansion"
---

What is Taylor expansion?
- Given a real-valued function f ∈ C∞(I) differentiable infinitely many times on an open interval I ⊆ R containing a point a, the power series
- $\sum _{n=0}^{\infty } {\frac{f^{(n)}(a)}{n!}}(x-a)^{n}$
- is called the Taylor series around the point a of the function f. When the Taylor series converges and coincides with f, we say that f is Taylor expandable.
- $\log(1+x) = \sum^{\infty}_{n=1} \frac{(-1)^{n+1}}n x^n\quad$
        - f(x) = log(1 + x)
        - f'(x) = 1/(1 + x)
        - f''(x) = -1 * (1 + x)^(-2)
        - f'''(x) = -1 * -2 * (1 + x)^(-3)
        - f^(n)(x) = (-1)^(n+1) (n - 1)! (1 + x)^(-n
        - a=0
- ${\displaystyle \log(1-x)=-\sum _{n=1}^{\infty }{\frac {x^{n}}{n}}}$
        - f(x) = log(1 - x)
        - f'(x) = -1 / (1 - x)
        - f''(x) = -1 * -1 * -1 * (1 + x)^(-2)
        - f'''(x) = -1 * -1 * -1 * -2 * -1 * (1 + x)^(-3)
        - f^(n)(x) = (n - 1)! (1 + x)^(-n)
        - a=0
- If we use this to approximate up to the second order, we get
- $\log(1+x) \approx x - {1 \over 2} x^2$
- $\log(1-x) \approx -x - {1 \over 2} x^2$

from  [[de Moivre-Laplace limit theorem]]

---
This page is auto-translated from [/nishio/テイラー展開](https://scrapbox.io/nishio/テイラー展開) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
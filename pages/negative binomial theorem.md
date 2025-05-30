---
title: "negative binomial theorem"
---

$(1-x)^{-d} = \sum_{n=0}^\infty \binom{n+d-1}{d-1}x^n$
other form:
- $1/(1-x)^{d+1} = \sum_{n=0}^\infty \binom{n+d}{d}x^n$

proof
To use mathematical induction, we assume that it is established at d and show that it is established at d+1

Formal derivative of a formal power series
$-d\cdot (1-x)^{-d-1} \cdot (-1) = \sum_{n=0}^\infty (n+1)\binom{n+d}{d-1}x^n$
Divide both sides by d to organize
$(1-x)^{-(d+1)} = \sum_{n=0}^\infty \frac{n+1}{d}\binom{n+d}{d-1}x^n$
- Definition of [binomial coefficient
- $\binom{n}{k} = \frac{n!}{k!(n-k)!}$
from (e.g. time, place, numerical quantity)
$\binom{n+d}{d-1} = \frac{(n+d)!}{(d-1)!(n+1)!}$
therefore
$\frac{n+1}{d}\binom{n+d}{d-1} = \frac{(n+d)!(n+1)}{d (d-1)! (n+1)!} = \frac{(n+d)!}{d! n!} = \binom{n + d}{d}$
To recap.
$(1-x)^{-(d+1)} = \sum_{n=0}^\infty \binom{n+(d+1) -1}{(d+1)-1}x^n$
Therefore, it is shown to hold at d+1

For d=1
$(1-x)^{-1} = \sum_{n=0}^\infty \binom{n}{0}x^n = \sum_{n=0}^\infty x^n$
This was shown in [infinite sum compression using the inverse of a formal power series#5f0a99d3aff09e00008d4555

[Polynomials and Formal Power Series (3) Linear Asymptotes and Formal Power Series | maspy's HP [https://maspypy.com/%e5%a4%9a%e9%a0%85%e5%bc%8f%e3%83%bb%e5%bd%a2%e5%bc%8f%e7%9a%84%e3%81%b9%](https://maspypy.com/%e5%a4%9a%e9%a0%85%e5%bc%8f%e3%83%bb%e5%bd%a2%e5%bc%8f%e7%9a%84%e3%81%b9%) e3%81%8d%e7%b4%9a%e6%95%b0%ef%bc%88%ef%bc%93%ef%bc%89%e7%b7%9a%e5%bd%a2%e6%bc%b8%e5%8c%96%e5%bc%8f%e3%81%a8%e5%bd%a2%e5%bc%8f]

---
This page is auto-translated from [/nishio/負の二項定理](https://scrapbox.io/nishio/負の二項定理) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
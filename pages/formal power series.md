---
title: "formal power series"
---

- Polynomial extended to have an infinite number of terms
    - Corresponding to an infinite number sequence
        - $F = \sum_{i=0}^\infty f_i x^i$
        - At this point, the formal power series $F$ is the [[generating function]] of the sequence [$ \{f_i\}
    - The operation of taking the coefficients of the nth order terms from a formal power series F is written as $[x^n]F$.
- There is a convenient property inherited from the polynomial
    - Additions and subtractions
    - multiplication
        - $[x^n](F\times G) = \sum_{i+j=n} ([x^i]F \times [x^j] G)$

[Polynomial and Formal Power Series (2) Derivation of Solutions by Expression Transformation | maspy's HP [https://maspypy.com/%e5%a4%9a%e9%a0%85%e5%bc%8f%e3%83%bb%e5%bd%a2%e5%bc%8f%e7%9a%84%e3%81%b9%e3](https://maspypy.com/%e5%a4%9a%e9%a0%85%e5%bc%8f%e3%83%bb%e5%bd%a2%e5%bc%8f%e7%9a%84%e3%81%b9%e3) %81%8d%e7%b4%9a%e6%95%b0%ef%bc%88%ef%bc%92%ef%bc%89%e5%bc%8f%e5%a4%89%e5%bd%a2%e3%81%ab%e3%82%88%e3%82%8b%e8%a7%a3%e6%b3%95]
    - [[Infinite sum compression using the inverse of a formal power series]]
    - [[Use of Factorization]]
    - By allowing F to factorize, we can use [[binomial theorem]] for each of them.
    - $F^T = (A + B)^T (C + D)^T = (\sum_i \binom{T}{i}A^iB^{T-i} ) \times (\sum_j \binom{T}{j} C^jD^{T-j})$
        - [exchange of product and sum
    - $F^T = (\sum_{i,j} \binom{T}{i}\binom{T}{j}A^iB^{T-i}C^jD^{T-j})$

    - [[Derivation of dp transition by cumulative sum]]
    - [[Derivation of DP to be returned]]
    - [[Application of the Law of Exchange and Repeated Squares]]

---
This page is auto-translated from [/nishio/形式的べき級数](https://scrapbox.io/nishio/形式的べき級数) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
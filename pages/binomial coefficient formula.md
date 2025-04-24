---
title: "binomial coefficient formula"
---

- eq1:
    - $\sum_{k=0}^n \binom{n}{k} = 2^n$
    - proof
            - [[binomial theorem]]
        - $(1 + 1) ^ n = \sum_{k=0}^n \binom{n}{k}$
        - $(1 + 1) ^ n = 2^n$

- eq2:
    - $\sum_{k=0}^n (-1)^k \binom{n}{k} = 0$
    - proof
            - [[binomial theorem]]
        - $(-1 + 1) ^ n = \sum_{k=0}^n (-1)^k 1^{n-k} \binom{n}{k} = \sum_{k=0}^n (-1)^k \binom{n}{k}$
        - $(-1 + 1) ^ n = 0^n = 0$

- eq3:
    - $\sum_{k=0}^{\lfloor n/2 \rfloor} \binom{n}{2k} = 2^{n-1}$
    - proof
        - from eq1, eq2
        - $(1 + 1) ^ n + (-1 + 1) ^ n = 2^n$
        - $(1 + 1) ^ n + (-1 + 1) ^ n = \sum_{k=0}^n \binom{n}{k} + \sum_{k=0}^n (-1)^k \binom{n}{k} = 2 \sum_{i=0}^{\lfloor n/2 \rfloor} \binom{n}{2i}$
        - Since they cancel each other when k is odd

- eq4:  [[Field hockey stick identity]]
    - $\sum_{i=0}^k \binom{n+i}{i} = \binom{n+k+1}{k}$

- eq5:
    - $\sum_{i=0}^k \sum_{j=0}^l \binom{i+j}{i} = \binom{k+l+2}{k+1}-1$
    - Pascal's triangulation
        - ![image](https://gyazo.com/161c01a67680a23524d71745a7cb5c38/thumb/1000)

- eq6:  [[Vandermonde's identity]]
    - $\sum_{i=0}^k \binom{n}{i}\binom{m}{k - i} = \binom{n+m}{k}$
    - special case(k=n, m=n)
        - $\sum_{i=0}^n \binom{n}{i}^2 = \binom{2n}{n}$

- eq6-2 [[ARC110D]]
    - $\sum_i \binom{i}{A}\binom{N-i-1}{B} = \binom{N}{A+B+1}$
    - Ballistic Interpretation
        - ![image](https://gyazo.com/9aabb603ccaadea2194910347eb52fa4/thumb/1000)

- eq6-3
    - $\sum_i \binom{A + i}{i}\binom{B + K - i}{K - i} = \binom{A + B + K + 1}{K}$
        - [[Attribute eq6-3 to eq6-2]]
        - [[Collapsing Duplicate Combinations]]

- eq7:
    - $\sum_{i=0}^k \binom{n+1}{i}\binom{m-i}{k - i} = \binom{n+m+1}{k}$
    - [[eq7-proof]]

    - [[Sum of binomial coefficients and Fibonacci]]
    - $\sum_i \binom{N-i}{i} = F_N$
    - ![image](https://gyazo.com/68fc51e0aad6ed0f251979427ce9fbfe/thumb/1000)

- eq8:
    - $r\binom{n}{r} = n\binom{n-1}{r-1}$
    - [https://mathtrain.jp/nikoukeisu](https://mathtrain.jp/nikoukeisu)



ref
    - [[A collection of counting techniques]]
- [Processing sums of binomial coefficients (formal power series) - Shino's Blog](https://shino-sky.hateblo.jp/entry/2020/04/16/230753)

---
This page is auto-translated from [/nishio/二項係数の公式](https://scrapbox.io/nishio/二項係数の公式) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
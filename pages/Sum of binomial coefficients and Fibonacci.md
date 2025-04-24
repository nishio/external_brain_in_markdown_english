---
title: "Sum of binomial coefficients and Fibonacci"
---

![image](https://gyazo.com/b2df8c9ce8cf3c362ec03a2b2839fd8b/thumb/1000)
$\sum_i \binom{N-i}{i} = F_N$
- where $F_0 = F_1 = 1, F_n = F_{n-2} + F_{n-1}$

![image](https://gyazo.com/68fc51e0aad6ed0f251979427ce9fbfe/thumb/1000)
$F_N = \sum_{i\ge 0} \binom{N-i}{i} = 1 + \sum_{i\ge 1} \binom{N-i}{i}$
$= 1 + \sum_{i \ge 1} \left(\binom{N-i - 1}{i} + \binom{N-i - 1}{i-1}\right)$
$= 1 + \sum_{i \ge 1} \binom{N-i - 1}{i} +  \sum_{i \ge 1} \binom{N-i - 1}{i-1}$
$= 1 + \sum_{i \ge 1} \binom{N-i - 1}{i} +  \sum_{j \ge 0} \binom{N - j - 2}{j}$
$= \sum_{i \ge 0} \binom{N-i - 1}{i} +  \sum_{j \ge 0} \binom{N - j - 2}{j}$
$= \sum_{i \ge 0} \binom{(N-1) - i}{i} +  \sum_{i \ge 0} \binom{(N-2) - i}{i}$
$= F_{N-1} + F_{N-2}$

- [[binomial coefficient]] and [[Fibonacci series]]

---
This page is auto-translated from [/nishio/二項係数の和とフィボナッチ](https://scrapbox.io/nishio/二項係数の和とフィボナッチ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
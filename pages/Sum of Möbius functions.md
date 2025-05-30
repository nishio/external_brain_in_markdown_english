---
title: "Sum of Möbius functions"
---


- Sum of [Möbius function
$ \sum_{d|n}\mu (d)=\left\{ \begin{array} {l}1 &(n=1) \\ 0 & (n>1)\end{array} \right.$


- $\sum_{k=0}^n (-1)^k \binom{n}{k} = 0$
        - [[binomial theorem]]
        - $(-1 + 1) ^ n = \sum_{k=0}^n (-1)^k 1^{n-k} \binom{n}{k} = \sum_{k=0}^n (-1)^k \binom{n}{k}$
        - $(-1 + 1) ^ n = 0^n = 0$

$\sum_{d|n} \mu(n/d) g(d) = \sum_{d|n} \mu(n/d) \sum_{l|d} f(l) = \sum_{d|n} \sum_{l|d} \mu(n/d)  f(l)$

$\sum_{d|n} \sum_{l|d} \mu(n/d)  f(l) = \sum_{l|n} f(l) \sum_{(n/d)|(n/l)} \mu(n/d)$

From eq1
$\sum_{(n/d)|(n/l)} \mu(n/d) =\left\{ \begin{array} {l}1 &(n/l=1) \\ 0 & (n/l>1)\end{array} \right.$


- [Mobius inversion formula and three applications - Math and Other Days](http://br-h2gk.hatenablog.com/entry/mebius_01)
from  [[Zeta transformation/Möbius transformation 20201105]]

---
This page is auto-translated from [/nishio/メビウス関数の和](https://scrapbox.io/nishio/メビウス関数の和) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
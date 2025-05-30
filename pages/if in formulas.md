---
title: "if in formulas"
---

- [[Iverson's notation]]   [[Iverson bracket]]
![image](https://gyazo.com/f34157fc1cb1fb44299121220725502a/thumb/1000)
- [Iverson's notation - Wikipedia [https://ja.wikipedia.org/wiki/%E3%82%A2%E3%82%A4%E3%83%90%E3%83%BC%E3%82%BD%E3%83%B3%E3%81%AE%E8%A8%98%E6%B3%](https://ja.wikipedia.org/wiki/%E3%82%A2%E3%82%A4%E3%83%90%E3%83%BC%E3%82%BD%E3%83%B3%E3%81%AE%E8%A8%98%E6%B3%) 95]
- $\sum_{x:0<x<N} f(x) = \sum_x f(x)[0<x<N]$
- Personally, I didn't like Kronecker's delta and indicator functions because they were hard to read, but I thought this notation was nice because it didn't make it too hard to read.
    - When neither True nor False has a non-zero value, it is easier to read if it is written in pieces rather than put together (B below).
        - A: $(x < 0 ? -1 : 1)$
        - B: $-1[x<0] + 1[x\ge0]$
        - C: $1 -2[x<0]$
        - D: $-1\delta_{x<0} + 1 \delta_{x\ge0}$
        - E: $1 - 2\delta_{x<0}$
- [Two notes on notation - Donald E. Knuth](https://arxiv.org/abs/math/9205211)
    - $[k \,\,\mathrm{even}] [k \,\,\mathrm{odd}] [k \,\,\mathrm{prime}] [k \,\,\mathrm{divedes} \,\,n]$

- [[Kronecker delta]]
![image](https://gyazo.com/b0463982ecb09c045acdd774d66c27d5/thumb/1000)
- [Kronecker's Delta - Wikipedia [https://ja.wikipedia.org/wiki/%E3%82%AF%E3%83%AD%E3%83%8D%E3%83%83%E3%82%AB%E3%83%BC%E3%81%AE%E3%83%87%E3%83%](https://ja.wikipedia.org/wiki/%E3%82%AF%E3%83%AD%E3%83%8D%E3%83%83%E3%82%AB%E3%83%BC%E3%81%AE%E3%83%87%E3%83%) AB%E3%82%BF]

- [[indicator function]]
![image](https://gyazo.com/86ae63fcd61a851bd0318e7e2afc1615/thumb/1000)
- [Directive function - Wikipedia](https://ja.wikipedia.org/wiki/%E6%8C%87%E7%A4%BA%E9%96%A2%E6%95%B0)

---
This page is auto-translated from [/nishio/数式でのif](https://scrapbox.io/nishio/数式でのif) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
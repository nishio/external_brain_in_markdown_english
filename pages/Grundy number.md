---
title: "Grundy number"
---

- Grundy number of losing states is 0
- The Grundy number of a state is the smallest non-negative integer other than the Grundy number of states from which it is possible to transition
    - mex: minimum excluded value

- The number of stones in a pile in [[Nim]] matches the Grundy number

- Why is it OK to XOR?
    - Let gi be the Grundy number for each mountain
    - Let g be the one joined by xor
    - $g = \bigoplus_i g_i$
    - Since we can prove that this g satisfies the Grundy number condition
    - half finished proof
        - Let m be the most significant bit of g. There are always an odd number of gi with m. Let g1 be one of them.
        - $g_1 \& m = m$
        - $g_1 \oplus g < g_1$, so transition is possible
        - $\left( \bigoplus_i g_i [i \neq 1] \right) \oplus (g_1 \oplus g) = \left(g_1 \oplus \bigoplus_i g_i [i \neq 1] \right) \oplus g = \left( \bigoplus_i g_i \right) \oplus g = g \oplus g = 0$
        - see [Theory of Grundy numbers (Nim numbers, Nimber)](https://www.creativ.xyz/grundy-number-1065/)

---
This page is auto-translated from [/nishio/Grundy数](https://scrapbox.io/nishio/Grundy数) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
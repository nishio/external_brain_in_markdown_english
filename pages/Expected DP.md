---
title: "Expected DP"
---

- Let f(x) be the expected number of operations from state x to N. f(N) = 0. We want to find f(1)
- Given f(x), find f(x-1)
    - Consider one step after the x-1 state
    - P probability of staying at x-1
    - (1 - P) with probability x
    - $f(x-1) - 1 = P f(x-1) + (1 - P) f(x)$
    - $(1 - P) f(x-1)   =  (1 - P) f(x) + 1$
    - $ f(x-1) = \left( (1-P) f(x) + 1\right) / (1 - P)$

[[ABC194]]D

---
This page is auto-translated from [/nishio/期待値DP](https://scrapbox.io/nishio/期待値DP) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
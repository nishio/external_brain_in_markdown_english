---
title: "doubling"
---

Given $f(x)$, I want to find $f^n(x)$ fast
- If the width of the definition and value range of f is D and the maximum value of n is N, we can pre-process O(D log N) to main process O(log N)
- pretreatment
    - Since $f^{2k}(x) = f^k(f^k(x))$, we obtain $f^{2k}$ by O(D) when $f^k$ is known
    - Since k=1 is known, we obtain in O(D log N) for k such that [$ k=2^m < N
- main processing
    - We can pick out only the 1's in [[binary expansion]] of n from the preprocessing results and synthesize them.
    - The length of the binary expansion is of logarithmic order

---
This page is auto-translated from [/nishio/ダブリング](https://scrapbox.io/nishio/ダブリング) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "loop detection"
---

- Given $f(x)$, I want to find $f^n(x)$ fast
    - The domain and value range of f are common finite sets
    - The starting point x is a single
    - If the size of the definition region is D and the maximum value of n is N, then the pre-processing O(D) can be made into the main process O(1)
- pretreatment
    - Prepare two arrays A and B
    - $A: f^i(x) \to i$
    - $B: i \to f^i(x)$
    - Fill this array by incrementing i
    - If Ai is not the initial value, it is a loop
    - Can be determined by constant order.
    - Worst case scenario, a loop is found by D
- main processing
    - i, Ai to the loop and the length of the path and the length of the loop until it enters the loop.
        - loop_start = Ai
        - loop_length = i - Ai
    - Constant Order $f^n(x) = (n - A_i) \% (i - A_i)$

---
This page is auto-translated from [/nishio/ループ検出](https://scrapbox.io/nishio/ループ検出) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
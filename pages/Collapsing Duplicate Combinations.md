---
title: "Collapsing Duplicate Combinations"
---

$\sum_i \binom{A + i}{i}\binom{B + K - i}{K - i} = \binom{A + B + K + 1}{K}$
This expression variant can be interpreted as a convolution of [[nested combination]] with another duplicate combination

- [[nested combination]] : number of ways to select k out of n, allowing for duplication
- $H^n_k = \binom{n + k - 1}{k}$

The left side is a duplicate combination that selects i from A+1 and K-i from B+1, and the convolution of this is a duplicate combination that selects K from A+B+2.
- $\sum_i \binom{A + i}{i}\binom{B + K - i}{K - i} = \sum_i H^{A+1}_i H^{B+1}_{K-i} = H^{A+B+2}_K = \binom{A + B + K + 1}{K}$
- ![image](https://gyazo.com/333dc6580cce8f6b5ef4b8cb6abdf495/thumb/1000)

from  [[binomial coefficient formula]]

[[ARC110D]]
- The problem of adding all patterns under the condition that the lower part of the binomial coefficient is fixed and the upper number has a constant sum.
- $\sum_i \binom{A + i}{i}\binom{B + K - i}{K - i} = \sum_i \binom{A + i}{A}\binom{B + K - i}{B}$
        - [[Lower fixed binomial coefficient → overlapping combination]]
    - Can you make a direct duplicate combination with the lower fixed?
    - $\sum_i \binom{A + i}{A}\binom{B + K - i}{B} = \sum_i H_A^{i+1} H_B^{K-i+1} = H_{A+B}^{K+2} = \binom{A + B + K + 1}{A+B}$
        - The math doesn't add up.
            - $\binom{A + B + K + 1}{A+B+1}$ should be
        - This is because the number of frames itself is changing, which is causing double counting.
        - If we think of adding a bounding ball, the bottom would likely be A+B+1, but then wouldn't we need to increase the top as well? I'm inclined to think that
        - In fact, this is fine because the boundary does not play the role of only a boundary (the ball can be placed in the same position as the boundary) by being a duplicate combination, but this may be confusing.

---
This page is auto-translated from [/nishio/重複組合せの畳み込み](https://scrapbox.io/nishio/重複組合せの畳み込み) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
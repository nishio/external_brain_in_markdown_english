---
title: "Attribute eq6-3 to eq6-2"
---

from  [[binomial coefficient formula]]
Attribute eq6-3 to eq6-2
        - $\sum_i \binom{A + i}{i}\binom{B + K - i}{K - i}$
        - $= \sum_i \binom{A + i}{A}\binom{B + K - i}{B}$ ... [[eq4-3]]
        - $= \sum_j \binom{j}{A}\binom{B + K - j + A}{B}$ ... A+i -> j
        - $= \sum_j \binom{j}{A}\binom{N - j -1}{B}$ ... A+B+K+1 -> N
        - $= \binom{N}{A + B + 1}$ ... eq6-2
        - $= \binom{A+B+K+1}{A + B + 1} = \binom{A+B+K+1}{K}$
---
This page is auto-translated from [/nishio/eq6-3をeq6-2に帰着](https://scrapbox.io/nishio/eq6-3をeq6-2に帰着) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
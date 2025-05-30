---
title: "ABC195D RE"
---

from [[ABC195]]
ABC195D RE
- Typical construction of the greed method [[Greed from those with fewer options.]].
    - The smallest box has the fewest options for the luggage it can hold.
    - Considering the case of one box, it is optimal to put in the largest value X that can be put in.
    - General,
        - If the optimal solution does not include X, then exchanging X for X increases its value, which is a contradiction
            - → thus X is always included in the optimal solution.
        - If there is an optimal solution where X is not in the smallest box, it is optimal to exchange it for a package in the smallest box.
        - Therefore, even if we decide to put X in the smallest box, we are guaranteed to obtain an optimal solution.
- Finding the largest of those satisfying the conditions in a large-size comparison can be done in logarithmic order with Range max in a segment tree, but for this problem constraint, even 50x50x50 is not a large size, so it is done naively.

---
This page is auto-translated from [/nishio/ABC195D RE](https://scrapbox.io/nishio/ABC195D RE) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
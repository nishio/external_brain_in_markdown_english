---
title: "Implementation to be inscribed on a sticky note"
---

- [[Ability to automatically inscribe long-form content on stickies]]

Made in early June [[regroup_split]].
    - [[Assistance in dividing long sentences into stickies]]
- Based on the dependency analysis, I tried to cut out unnecessary words on a rule basis.

Late Aug.
- When considering CRFing of [[RAKE]], two occurrences are global features
    - Sticky note division does not care about the number of occurrences.
            - The concept of [May be duplicated
    - That's why it's suitable for CRF.
- subtractive problem
    - Put a break or cut it out longer.
        - This part of the composition is similar to RAKE's key phrase candidate creation.
    - Removal or rewriting in cut-out fragments
        - While RAKE was chopped finely and then attached, this style is shaved from a larger piece.

---
This page is auto-translated from [/nishio/付箋に刻む実装](https://scrapbox.io/nishio/付箋に刻む実装) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
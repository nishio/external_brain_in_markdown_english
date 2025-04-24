---
title: "abc113_d"
---

[https://atcoder.jp/contests/abc113/tasks/abc113_d](https://atcoder.jp/contests/abc113/tasks/abc113_d)
- Thoughts.
    - In a naive way, think about how many ways you can fill the empty space for each way of repeating the compatibility and making 1 into K.
        - I don't think this one will make it.
    - width 8 height 100
        - Less than 2^7 lines per line.
        - First, we should foolishly count up how many ways "i goes to j".
    - DP with "how many ways is 1 in line a in b?"
    - Read the K-th last.
    - Side note: I don't feel the need to do this since it's 8x8x100 in this case, but if it's larger. It's a power of the transition matrix, so it can be doubled.
- Official Explanation OK
    - The official explanation does not pre-calculate transition probabilities and does a full search, but that is still good enough.
    - You might have noticed that if you tried a smaller value, you'd actually get the [[Fibonacci series]].

---
This page is auto-translated from [/nishio/abc113_d](https://scrapbox.io/nishio/abc113_d) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
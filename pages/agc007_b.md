---
title: "agc007_b"
---

[https://atcoder.jp/contests/agc007/tasks/agc007_b](https://atcoder.jp/contests/agc007/tasks/agc007_b)
- Thoughts.
        - [[Think in order from smallest to largest]]
    - When N=2
        - 1,2 would be OK with 1,3 2,1
        - If 2,1, then 1,2 3,1 is OK.
    - Is it tricky to have the middle come to the edge with N=3?
        - 1,3,2 would be 1,4,6 5,4,1
    - First, 1,2,3 3,2,1 as a baseline, all to be N+1
    - Multiply all of this by X. It's easier to move numbers up and down, just think about moving them up.
    - Increase ap2 by 1, ap3 by 2...
    - This is the maximum +19999, so if you keep X at 20,000, it won't be reversed.
    - 20000 x 20000 fits the problem conditions.
    - Side note: if it didn't fit in the problem conditions, I would have had to move b and cram it in, but it doesn't seem to be required to go that far.
- Official Explanation OK

---
This page is auto-translated from [/nishio/agc007_b](https://scrapbox.io/nishio/agc007_b) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
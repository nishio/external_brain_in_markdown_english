---
title: "abc099d"
---

[https://atcoder.jp/contests/abc099/tasks/abc099_d](https://atcoder.jp/contests/abc099/tasks/abc099_d)
- The problem of aligning to one color at the first cost of each excess of 3 separately.
- Three independent problems? I thought so, but it's tricky that the aligned results should not be the same color.
    - If we check the three smallest costs for each of them, we can search for the smallest from the 27 streets in all.
- After dividing into three, the squares are just under 10^5 and the colors are 30
    - I wonder if it would be better to ask for the cost of each color foolishly.
- Official Explanation
    - 30 x 29 x 28 streets > 10^5 squares for 10^4, and when I check the 10^9 squares for 10^4, I can't make it.
    - Count the number of pieces of each color in each of the three blocks in the preprocessing
    - My method is pre-processing to find the cost of aligning each color in each of the three blocks, the order of calculation is the same.

---
This page is auto-translated from [/nishio/abc099d](https://scrapbox.io/nishio/abc099d) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
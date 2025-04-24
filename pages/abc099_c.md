---
title: "abc099_c"
---

[https://atcoder.jp/contests/abc099/tasks/abc099_c](https://atcoder.jp/contests/abc099/tasks/abc099_c)
- The number of seeds of the amount of money that can be withdrawn at one time is about 20 at most.
- I wonder if I can make it in time to explore from N to width first.
    - Assuming, of course, that you would prune branches if they were "already visited by shorter means".
    - Each vertex enters the search waiting list at most once, and 20 cases are searched from the ones entered, or about 2 x 10^6
    - It's an ABC C problem, so it's not that hard.
- Official Explanation
    - It doesn't say if the above method is the right one.
    - The notional solution method is to find the minimum value for i less than or equal to N by finding the cost of expressing it with only 6 and 1 and the cost of expressing the rest with only 9 and 1.


---
This page is auto-translated from [/nishio/abc099_c](https://scrapbox.io/nishio/abc099_c) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "abc119_c"
---

[https://atcoder.jp/contests/abc119/tasks/abc119_c](https://atcoder.jp/contests/abc119/tasks/abc119_c)

- Thoughts.
        - [[The order of operation is irrelevant.]]
        - Cost is the same whether combined and then stretched or stretched and then combined
        - So we only need to think about the bonding first.
    - Since there are 8 bars, there are 2^8 ways to choose which one to join, this is not necessary to DP
        - Oops, wrong problem condition, the goal is not to get one specific length, but three.
    - 4^8 ways to put it in any of the 3 groups or not, less than 10^5, OK to search all of them.
        - The objective length for each group does not lose generality by assuming descending order
        - Find the length of the combined bamboo, add the absolute difference from the target value to the score, and return the smallest one.
- Official Explanation
    - The policy is the same
    - You can't extend nothing." sure. Missed this one, so I'm going WA on this one.

---
This page is auto-translated from [/nishio/abc119_c](https://scrapbox.io/nishio/abc119_c) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
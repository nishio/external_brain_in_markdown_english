---
title: "ARC091B"
---

[D - Remainder Reminder](https://atcoder.jp/contests/arc091/tasks/arc091_b)
- ![image](https://gyazo.com/fcef21e76d5fe9ebcd49ecfe88f6fad6/thumb/1000)
- Thoughts.
    - A naive search for a number that satisfies the condition is 10^10, no.
    - Calculated for each b
        - 0 if less than k
        - If larger, divide N by b → q, r
        - ret = q * (b - k)
        - If r > k, ret += r - k
- Official Explanation OK
    - There's one discrepancy, but I'm sure it can be fixed quickly with a test case.

[[ARC091]]
[[ARC]]

---
This page is auto-translated from [/nishio/ARC091B](https://scrapbox.io/nishio/ARC091B) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
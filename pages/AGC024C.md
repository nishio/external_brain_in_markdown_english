---
title: "AGC024C"
---

[C - Sequence Growing Easy](https://atcoder.jp/contests/agc024/tasks/agc024_c)
![image](https://gyazo.com/d9599e3ba6f5347d1b6783f3d3799ca0/thumb/1000)
- Thoughts.
    - You can't increase the number at the top.
    - Overall, it can only be increased to i-1.
    - When a line is drawn from the goal value to the right, the value on the right never crosses that line. Because the only way to get to that value is to repeat the operation from further in front.
    - So classify by i-Ai, make sure it is monotonically non-decreasing, find the number of times from the start and end points, add them up, linear order
- Official Explanation
    - Instead of classifying it, they're doing it in a simpler way.
        - +1 if +1 compared to the last time, +1 for the number of moves
            - This corresponds to my "same classification"
        - If there is more than that, it is NG.
            - This corresponds to "not monotonically non-decreasing"
        - Otherwise, hands + Ai
            - It takes more moves to increase from zero before that.

[[AGC024]]

---
This page is auto-translated from [/nishio/AGC024C](https://scrapbox.io/nishio/AGC024C) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "ACLPC L"
---

from [[AtCoder Library Practice Contest]]
ACLPC_L
[L - Lazy Segment Tree](https://atcoder.jp/contests/practice2/tasks/practice2_l)
- ![image](https://gyazo.com/b616e54f13c09c43d58d90950621c511/thumb/1000)
    - [[number of events (e.g. accidents, crimes, meetings, housing starts, hits on a web page)]]
- Maps (number of 0's, number of 1's, number of falls) to a binary sequence.
    - This value can be calculated for the combined two columns from this value alone
        - (Feels like when you build a DP)
:

```
f((a1, b1, c1), (a2, b2, c2)) = (a1 + a2, b1 + b2, c1 + c2 + b1 * a2)
```

    - This is obvious when you calm down and think about it.
        - As for the number of 0's and the number of 1's, it is just a sum
        - The number of falls is added to the original number of falls for each plus the amount increased by bonding
        - The amount increased by this union is the number of "tumbling pairs" divided into each column, so it is "the number of 1's in the left column" multiplied by "the number of 0's in the right column".
    - This composite operation f is [[monoidal]] because it is associative and has unitary source (0, 0, 0)
        - In fact, it is a group: [The group structure followed by the number of inversions of a binary string - Qiita](https://qiita.com/hamko/items/92660ac5aed9df4d346d)
    - Therefore, this value can be used for the value range of the segment tree
- The action is to flip the bits in the column, but what happens to the values at this time?
    - `(y, x, x * y - z)`
    - There are x * y pairs of different numbers, of which z pairs are inverted, and if you flip them, the rest are inverted pairs [[superfluous event]].

---
This page is auto-translated from [/nishio/ACLPC L](https://scrapbox.io/nishio/ACLPC L) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
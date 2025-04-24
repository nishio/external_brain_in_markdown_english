---
title: "ARC064A"
---

[C - Boxes and Candies](https://atcoder.jp/contests/abc048/tasks/arc064_a)
- ![image](https://gyazo.com/c84644ac1d4a36f657c731f52c30b6eb/thumb/1000)
- Thoughts.
    - Count the number of moves until the sum exceeds x, the constraint violation penalty, 0.
    - When the violation points are independent, there is no other option but to reduce them by the amount of the penalty.
    - If consecutive, two penalties can be reduced at the same time
    - Best to reduce the two ends until the end is zero.
        - It's only 2 less than the maximum.
    - So we can calculate the penalty in linear order and crush it from the end in linear order.
- Official Explanation
    - Same policy of filling in from the edges.

[[ARC064]]

---
This page is auto-translated from [/nishio/ARC064A](https://scrapbox.io/nishio/ARC064A) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
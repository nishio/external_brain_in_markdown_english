---
title: "tenka1_2018_C"
---

[C - Align](https://atcoder.jp/contests/tenka1-2018-beginner/tasks/tenka1_2018_c)
- ![image](https://gyazo.com/ded3891efa2ce77c3e1abc6275cdbce5/thumb/1000)
- Thoughts.
    - Same no matter how you do it when you have two.
    - When there are three, do you bring the largest value to the middle or the smallest value to the middle? Either one is the same.
    - When 4
        - Maximum and minimum values should not be placed on the edge
        - After that, zigzagging is OK.
    - in general
        - When the number of four is monotonically increasing, it is always better to swap the middle two and zigzag
        - For zigzag piles other than the edge, swapping them around does not change the result.
        - How should we think about the edges...
            - Always better to swap if the end is on the smaller side of the zigzag and lower than the valley with the zigzag
            - If you have an even number of pieces, just split them in half, large and small, and end up with two on the boundary.
            - If you have an odd number of pieces, do you want more large or more small...
                - You want to try a small row to make sure, if different, try both.
    - The above considerations yield an answer in sorted linear order.
- Official Explanation
    - Roughly the same feeling

---
This page is auto-translated from [/nishio/tenka1_2018_C](https://scrapbox.io/nishio/tenka1_2018_C) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
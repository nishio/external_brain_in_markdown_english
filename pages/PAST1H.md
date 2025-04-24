---
title: "PAST1H"
---

from  [[First Algorithm Practical Skills Test]]
PAST1H
[h - summary sale](https://atcoder.jp/contests/past201912-open/tasks/past201912_h)
- Thoughts.
    - Sell 200,000 different products 200,000 times
    - We want to lower the cost of inventory checks.
        - Query 2,3 with successful sales numbers a,b
            - The number of inventory remaining when sold in bulk will update this value.
        - Pre-calculate the minimum value of the range for queries 2 and 3
            - Look at this value to see if query 2 or 3 can be done.
        - For query 1, if it is an odd number, x-a-b, if not, x-a is the remaining inventory.
- Official Explanation OK

---
This page is auto-translated from [/nishio/PAST1H](https://scrapbox.io/nishio/PAST1H) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
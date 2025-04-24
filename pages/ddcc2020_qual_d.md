---
title: "ddcc2020_qual_d"
---

[https://atcoder.jp/contests/ddcc2020-qual/tasks/ddcc2020_qual_d](https://atcoder.jp/contests/ddcc2020-qual/tasks/ddcc2020_qual_d)
Thoughts.
- I want to replace two adjacent columns of numbers with a product to maximize the number of times to get to a single digit.
    - PS: Wrong problem condition, sum, not product
- Do you want to avoid conversions that reduce the number of digits as much as possible?
- The whole thing is 10^15 digits, so even if you can get the best conversion location in constant order, you won't get it in time.
- They want to take advantage of the fact that they have the same number lined up.
    - A sequence of 1s, for example, can simply be converted to a number of times its length.
    - Row 2 is already difficult.
        - Because something other than 2 will appear when you convert it.
        - Is it enough to show that a mid-column conversion is not optimal?
        - I would like to observe the optimal solution by force for a short sequence of 2
- Official Explanation
    - Can be shown to be independent of the order of operations
    - Oh, I misunderstood the problem condition, it was a sum, not a product.
    - It can be shown that the number of times is constant regardless of the choice of operation.

---
This page is auto-translated from [/nishio/ddcc2020_qual_d](https://scrapbox.io/nishio/ddcc2020_qual_d) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
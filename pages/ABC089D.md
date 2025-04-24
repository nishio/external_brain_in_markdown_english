---
title: "ABC089D"
---

[D - Practical Skill Test](https://atcoder.jp/contests/abc089/tasks/abc089_d)
![image](https://gyazo.com/a49eb876a37bc8c277e28d5080a06365/thumb/1000)
- Thoughts.
    - The query is 10^5
    - The size of the board is 9,000
    - A linear order will not be enough to find the requested value from the board in time.
    - Even with constant order, if you have to do "10^5 times, increasing by 1 from 1 to 90000" as a nasty problem, you still won't be able to do it in time.
    - I mean, the number is 90,000 and the query is 100,000, so we should expect a lot of overlap.
    - In other words, where costs add up, they should be cashed.
    - First, create an [[inverse mapping table]] from numbers to coordinates in linear order
    - Then, for each remainder divided by D, make a [[cumulative sum]] of the D books.
        - This would be of linear order if the inverse mapping table
    - If you prepare this far, one query will be of constant order.
- Official Explanation OK

[[ABC089]]D

---
This page is auto-translated from [/nishio/ABC089D](https://scrapbox.io/nishio/ABC089D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
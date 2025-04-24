---
title: "PAST1N"
---

[N - landscaping](https://atcoder.jp/contests/past201912-open/tasks/past201912_n)
![image](https://gyazo.com/8b99c6809b86f9fe2fee2cd6710f2b46/thumb/1000)
- Thoughts.
    - I want to minimize the sum of the removal costs of N overlapping intervals by moving intervals of length C
    - I haven't proved it properly, but I think the starting point of C is either 0 or the endpoint of the other interval + 1.
    - OK if the cost can be calculated in smaller orders for each section.
    - Finding overlapping intervals is a linear order if done naively.
    - For two sets of numbers, given their respective inequality constraints, do you want to enumerate those that satisfy both?
        - Sometimes it's too late for enumeration, or for example, the case where all the sections overlap.
    - Sort by mixing (position, ID, isStartPoint) of start and end points
    - Interval C is [[inchworm law]] (larger side)
    - If you advance the endpoint and step on the starting point, add the cost.
    - If you advance the starting point and step on the end point, reduce the cost.
    - Which one to advance is determined by "whether the starting point is advanced to a length less than C
    - This is now obtained in linear order.
- Official Explanation OK

- [[First Algorithm Practical Skills Test]]

---
This page is auto-translated from [/nishio/PAST1N](https://scrapbox.io/nishio/PAST1N) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Interval Scheduling"
---

There are N intervals (start Si end Ti). We want to select as many intervals as possible so that there are no common parts.

It is known that the greedy method of choosing intervals ($\argmin_i T_i$) in the [[Earliest end]] in turn yields the optimal solution.

Why?
- Choose one of the first sections
    - If there is more than one section, you can choose one of them.
    - Let's call "the end of the last selected interval" F.
    - The selection that chooses the interval with the earliest termination has the smallest F of the one possible selections. (Fmin_1).
    - Segments with a start before F are not selectable in the future.
        - Because it intersects with the selected section.
- Consider that k intervals have already been chosen and the k+1st is to be chosen.
    - When there is more than one interval with a start after F, one can be selected from them.
    - If one can pick one with some F > Fmin_k, one can also pick one with F = Fmin_k.
        - Because you can choose the one that is chosen.
    - Select the interval with the earliest end from the intervals with a start after Fmin_k
        - This is the smallest F of the k+1 possible choices. (Fmin_{k+1})
- If there is a way to choose n intervals by mathematical induction, we can choose n by this method

[http://www.prefield.com/algorithm/misc/interval_scheduling.html](http://www.prefield.com/algorithm/misc/interval_scheduling.html)


---
This page is auto-translated from [/nishio/区間スケジューリング](https://scrapbox.io/nishio/区間スケジューリング) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
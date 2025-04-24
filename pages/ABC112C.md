---
title: "ABC112C"
---

[C - Pyramid](https://atcoder.jp/contests/abc112/tasks/abc112_c)
- ![image](https://gyazo.com/26703e70d37462b7f880bcd2126d9014/thumb/1000)
- Thoughts.
    - It's tempting to ignore the 0-height vertex, but that's no good because you can create a pattern that can't be determined without hinting at the 0-height vertex.
    - If there are three points of the same height, that's definite, depending on the placement.
    - ![image](https://gyazo.com/fc11dd9f3a19cd2f8c5de5d6d876d47d/thumb/1000)
    - Hmmm, it's possible that there are no dots of the same height at all.
    - Constraints created by a single observation point
        - I am the pinnacle, huh?
        - There is 1 high vertex in 8 squares around you, or...
        - and for every square, if there is a vertex there, there will be a constraint on how high it can be.
    - The constraint of the second observation point makes most vertices impossible.
    - It is not too late to update 100 observation points for 100 x 100 squares.
    - In fact, the number of possible candidates is drastically reduced after the second one, so we could even put that on the list and just update that part of the list.
- Official Explanation
    - There was proof that "not all observation points are zero."
    - When 0, the form of the constraint is different.
        - Inequality Constraints.
    - The style is to first create position and height pairs at non-zero observation points, and then eliminate inconsistencies.

---
This page is auto-translated from [/nishio/ABC112C](https://scrapbox.io/nishio/ABC112C) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
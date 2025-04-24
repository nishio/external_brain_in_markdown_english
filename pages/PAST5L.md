---
title: "PAST5L"
---

[L - T erase](https://atcoder.jp/contests/past202012-open/tasks/past202012_l)
![image](https://gyazo.com/9d3a4c94bb870908ddb459d35f181fb0/thumb/1000)
- Initial Considerations
    - There are multiple points of appearance, and the best result may or may not be achieved depending on which one is prioritized for elimination.
    - ![image](https://gyazo.com/b7c90ebc80943d64f71cf6ecc519c5df/thumb/1000)
    - Hmmm, is there some kind of greedy way of deciding?
    - If there is no overlap, does it make a difference which way you do it from?
        - Still, 33 overlaps at worst; you can't do 33 factorials.
    - I wonder if a non-decisional automaton could handle this in a nice way.
    - hold (e.g. telephone button)
- Official Explanation
        - [[Interval DP]]
    - How do we realize that this issue is section DP...
        - [[Value determined for column]]
            - [[Value determined for column → DP in section of column]]

---
This page is auto-translated from [/nishio/PAST5L](https://scrapbox.io/nishio/PAST5L) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
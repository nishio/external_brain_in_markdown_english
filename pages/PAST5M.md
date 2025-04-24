---
title: "PAST5M"
---

[M - Shipping Bars](https://atcoder.jp/contests/past202012-open/tasks/past202012_m)
![image](https://gyazo.com/d4601d3337d3e2a1f3a3e17ce6c0b8da/thumb/1000)
- Initial Considerations
    - 2^N not to cut, because N is 10^5 or bigger.
    - Will it be a 2N DP?
        - (after neg. verb stem) seeming impossible
    - How about a style that ticks once for maximum length and then moves forward one tick at a time?
        - Shakitori-legal approach, searching only for likely solutions
        - I wonder if the lower limit will gradually increase, and if the search space will become rather small because it is not necessary to search for the area that becomes smaller than the lower limit...
- Official Explanation
        - [[Maximization with bisection search.]]
    - To be continued, once I think about it on my own after this.

---
This page is auto-translated from [/nishio/PAST5M](https://scrapbox.io/nishio/PAST5M) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
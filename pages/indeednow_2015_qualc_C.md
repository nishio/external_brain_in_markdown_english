---
title: "indeednow_2015_qualc_C"
---

[C - Thu](https://atcoder.jp/contests/indeednow-qualb/tasks/indeednow_2015_qualc_3)
- ![image](https://gyazo.com/2908a294054ddde75f3d5615245d2b40/thumb/1000)
- Thoughts.
    - The simple way to do it is to repeat "take the smallest adjacent vertex".
    - But this way, when you have an edge from vertex 1 to 10^5 other edges, you'll have to choose from 10^5 edges about 10^5 times, so you won't make it in time.
    - So we need a way to get the minimum value without searching and sorting every time.
        - [[priority queue]] Right.
    - [[Official Explanation OK]]

---
This page is auto-translated from [/nishio/indeednow_2015_qualc_C](https://scrapbox.io/nishio/indeednow_2015_qualc_C) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
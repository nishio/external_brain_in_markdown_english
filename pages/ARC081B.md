---
title: "ARC081B"
---

[D - Coloring Dominoes](https://atcoder.jp/contests/arc081/tasks/arc081_b)
- ![image](https://gyazo.com/075c4e162e79f797c7792309efe6fa3b/thumb/1000)
- Thoughts.
    - You are given a highly flexible representation of the placement of the dominoes, but essentially all you need is a "place them vertically" or "place two horizontally" column. Convert to that first.
    - when the foreground is horizontal
        - Verticals have only one way to paint.
        - The sides are three ways: ba, bc, and ca, with ab in the foreground.
    - when the foreground is vertical
        - Vertical is two ways
        - There are two sides, bc and cb, with a in the foreground.
    - The first three ways are vertical, and the sixth way is horizontal.
    - The rest can be calculated in any order.
        - [[Only last minute is relevant.]]
    - [[Official Explanation OK]]



---
This page is auto-translated from [/nishio/ARC081B](https://scrapbox.io/nishio/ARC081B) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
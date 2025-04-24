---
title: "abc120_d"
---

[https://atcoder.jp/contests/abc120/tasks/abc120_d](https://atcoder.jp/contests/abc120/tasks/abc120_d)
- Thoughts.
    - Count the number of pairs that cannot go back and forth.
        - [[have an after-event]]
        - Islands that can come and go = connected
        - If the size of the connected component is known [[trigonometric number]].
        - [[time reversal (physics)]] The composition of the edges is increasing one by one.
    - Should I use [[UnionFind]] to find the connected components?
    - The process of finding the size of the connected component will not be completed in time if the root of each vertex is checked, so it is necessary to have the size in the form of root→size.
- Official Explanation
    - OK
    - UnionFind says size is O(1), but doesn't that mean it's implemented that way?

---
This page is auto-translated from [/nishio/abc120_d](https://scrapbox.io/nishio/abc120_d) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
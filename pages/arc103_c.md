---
title: "arc103_c"
---

[E - Tr/ee](https://atcoder.jp/contests/arc103/tasks/arc103_c)
![image](https://gyazo.com/83c5876ac46283a866b2c1c3e8a07dfe/thumb/1000)
- Thoughts.
    - If no connected component of size 1 can be created by removing any edge, the second vertex from the edge has a rank greater than or equal to 3.
    - When you can make size x, you can also make size N-x-1
    - When size N-1 cannot be made, there should not be a point with rank 1.
        - Recheck the conditions, this is not possible because it is a tree, not an arbitrary graph.
    - [[doing]]

---
This page is auto-translated from [/nishio/arc103_c](https://scrapbox.io/nishio/arc103_c) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
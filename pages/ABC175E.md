---
title: "ABC175E"
---

[E - Picking Goods](https://atcoder.jp/contests/abc175/tasks/abc175_e)
- ![image](https://gyazo.com/e57957740dbbd37050b698607cd44710/thumb/1000)
- Thoughts.
    - Minimum cost flow?
        - This condition is difficult.
        - > Takahashi-kun can pick up items in the squares he passes (including the start and goal). However, you can only pick up 3 items in the same row of squares. If there is an item in a square you pass, you may not pick up that item.
- Official Explanation
    - r, c, plus "number of items picked up" DP in three dimensions
- A new thought.
        - Even when solving with [[least-cost current]], "only 3 pieces can be picked up" is 3-dimensional if it is expressed in terms of graph vertices.
    - And it is computationally less expensive to solve with DP than to solve as least cost flow cost.
    - First, this is [[The problem of maximizing the score of a pathway]].
        - And if there are no "up to 3", then the type of "score is obtained from only the last vertex of the pathway".

- [[unAC]]

---
This page is auto-translated from [/nishio/ABC175E](https://scrapbox.io/nishio/ABC175E) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
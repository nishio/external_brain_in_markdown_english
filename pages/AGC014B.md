---
title: "AGC014B"
---

[B - Unplanned Queries](https://atcoder.jp/contests/agc014/tasks/agc014_b)
- ![image](https://gyazo.com/6964219a87b15e25515e43510edb342e/thumb/1000)
- Thoughts.
    - For example.
        - If the query were a single query, it would be impossible regardless of the shape of the tree.
        - Impossible unless the two queries overlap completely.
        - If the query is 3 queries ab, bc, ca, then ok.
    - In other words, it looks good if it's a cycle.
        - Multiple pieces are possible.
        - In other words, count the number of times it appears at the end of the query, and if it's an even number of times, it's OK.
        - Proof.
            - Odd edges are always formed around the points that the query touches only an odd number of times.
            - Since it is a tree, the path connecting the two points is unique
                - When there are ab and bc, the paths that follow abc in this order but not on ac go back and forth twice.
- Official Explanation
    - Policy OK
    - Proof is considered in mod 2 with rooted trees

    - [[problem partitioning]]
        - [[Update tree edge labels]]
            - [[You don't have to update the edge labels, just look at the endpoints.]]

---
This page is auto-translated from [/nishio/AGC014B](https://scrapbox.io/nishio/AGC014B) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
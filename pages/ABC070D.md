---
title: "ABC070D"
---

[D - Transit Tree Path](https://atcoder.jp/contests/abc070/tasks/abc070_d)
- ![image](https://gyazo.com/7747dc17e290d49629796ab6d7387f3a/thumb/1000)

- Thoughts.
    - K is one whole
    - That is, if we pre-calculate the distances from K to all vertices, the query just adds up the lengths of the two paths
    - We can DFS K as the starting point and determine the distance of each vertex
- Official Explanation
    - The policy is the same
        - [[There is one path between two vertices of a connected graph with no closed path]]
    - MLE with graphs with adjacency matrices
        - I don't usually hold it that way, so I'm not into it.

---
This page is auto-translated from [/nishio/ABC070D](https://scrapbox.io/nishio/ABC070D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
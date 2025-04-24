---
title: "ABC054C"
---

[C - One-stroke Path](https://atcoder.jp/contests/abc054/tasks/abc054_c)
![image](https://gyazo.com/d709f17d39572be0e97aa653b895f2fe/thumb/1000)
![image](https://gyazo.com/dfc5b8b3a15d7b70e7ca6c8340950de9/thumb/1000)

- Thoughts.
        - [[Estimating computational quantities]]
        - The number of vertices is 8, so it's OK to search all of them in the factorial.
    - I usually have graphs with adjacency lists, but this time it's an adjacency matrix.
    - For each permutation, just check "Does it have an edge?
    - If there's no edges along the way, it's impossible to search ahead, so I'd prefer to use depth-first search to prune the branches.
- Official Explanation OK
    - I'm assuming the solution above, but bit DP says it's O(N^2 2^N).
        - You have the number of cases where you start at point X for all subsets, follow them all, and end at point Y.

---
This page is auto-translated from [/nishio/ABC054C](https://scrapbox.io/nishio/ABC054C) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
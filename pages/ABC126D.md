---
title: "ABC126D"
---

[D - Even Relation](https://atcoder.jp/contests/abc126/tasks/abc126_d)
![image](https://gyazo.com/e04b1343acc9d7bf636fa218acfe0162/thumb/1000)
- Thoughts.
    - Focus on one point, which is white.
    - The point that can be traced in one step from that point must be black.
    - The point that can be traced in one step from black must be white.
    - So you can paint alternately at DFS.
    - Why this is a good idea
        - Because the sum of the distances from the root to any two points is equal to the even distance between those two points
    - I think I saw something about a similar process, but I'm not sure what it was...
        - Yes, [[bipartite graph decision]].
    - [[Official Explanation OK]]

[[ABC126]]

---
This page is auto-translated from [/nishio/ABC126D](https://scrapbox.io/nishio/ABC126D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
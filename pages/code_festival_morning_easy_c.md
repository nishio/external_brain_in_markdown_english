---
title: "code_festival_morning_easy_c"
---

[https://atcoder.jp/contests/code-festival-2014-morning-easy/tasks/code_festival_morning_easy_c](https://atcoder.jp/contests/code-festival-2014-morning-easy/tasks/code_festival_morning_easy_c)

- Thoughts.
    - The question of whether there exists a shortest path from s to t that is exactly half the distance at a vertex along the way
    - Shortest paths exist in exponential order and cannot be enumerated and then examined.
    - Let's first find the distance between s,t and then find out if there's a vertex half that distance.
    - When the Dijkstra method is used to find the distance of s,t, the distance to the shorter vertex is already identified
        - Choose exactly half the distance from there.
            - This is the worst case, there are almost N of them.
        - The distance between t and s is obtained in the same way, or
        - We can check if there exists a v such that d(s,v)=d(t,v)=d(s,t)/2
            - This is a linear order
        - The computational complexity is that of the [[Dijkstra method]], so it can be used in time.
- Official Explanation
    - nashi (Pyrus pyrifolia, esp. var. culta)

---
This page is auto-translated from [/nishio/code_festival_morning_easy_c](https://scrapbox.io/nishio/code_festival_morning_easy_c) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
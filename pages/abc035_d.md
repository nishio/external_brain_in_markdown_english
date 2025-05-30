---
title: "abc035_d"
---

[https://atcoder.jp/contests/abc035/tasks/abc035_d](https://atcoder.jp/contests/abc035/tasks/abc035_d)
- Thoughts.
    - Sometimes it is more profitable to pay the travel cost and go to another city than to stay in the first city for T minutes and keep getting A1.
    - At this time, the destination city must have a larger Ai to gain
    - When moving from one city to another, staying in the middle of the city is not an optimal solution.
    - Therefore, "go to town i in the shortest distance, spend some time and come back" is the optimal solution, and find out which i is the correct answer.
    - First, use the [[Dijkstra method]] to find the shortest distance to each town
    - Choose the largest score
- Official Explanation
    - WA: Problem condition misunderstanding, road is not two-way
    - The way home is not a single starting point
    - If we invert the → edge and do the Dijkstra method, we can also do the shortest path with a single endpoint.

---
This page is auto-translated from [/nishio/abc035_d](https://scrapbox.io/nishio/abc035_d) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
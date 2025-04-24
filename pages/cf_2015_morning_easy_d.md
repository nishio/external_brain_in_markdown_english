---
title: "cf_2015_morning_easy_d"
---

[https://atcoder.jp/contests/code-festival-2015-morning-middle/tasks/cf_2015_morning_easy_d](https://atcoder.jp/contests/code-festival-2015-morning-middle/tasks/cf_2015_morning_easy_d)
- Thoughts.
    - The problem of making a string into two substring repetitions
    - I don't know where the second starting point is.
    - There's two ways to read it, depending on which one you skip when you're in a discordant situation.
    - hmm
    - Theoretically, the second starting point could be from the second letter, but then the cost is N-2 at best, right?
    - Consider the second trio of starting points n, points of interest i, j
    - Start from (n, 0, n) and reach (n, n, N) to reach the goal
    - If Si=Sj, we can increment i,j at zero cost.
        - If not, you can increment one at cost 1.
    - In other words, this is the [[shortest path problem]], which can be solved using the [[Dijkstra method]]. The graph is not explicitly constructed.
    - Since N is 100, the number of vertices is about 5 x 10^5. There is plenty of room.
- No official commentary

---
This page is auto-translated from [/nishio/cf_2015_morning_easy_d](https://scrapbox.io/nishio/cf_2015_morning_easy_d) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
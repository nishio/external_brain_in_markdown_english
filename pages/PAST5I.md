---
title: "PAST5I"
---

[I - Evacuation Plan](https://atcoder.jp/contests/past202012-open/tasks/past202012_i)
![image](https://gyazo.com/01513f650068f7946cc04b839444666a/thumb/1000)
- Initial Considerations
    - You can only move from higher elevations to lower elevations.
        - directed graph
    - Lots of goals.
        - Bundling around cost 0?
                - [[One Goal.]]
        - One to all [[Dijkstra method]] from each goal?
        - Let's do the latter, and if not, let's do the former.
    - Consideration complete
- mounting
    - If we were to do the Dijkstra method anyway, the additional man-hours to implement the former would not be significant, so we decided there was no advantage to doing the latter.
    - Additional code to implement the former : `(1)`.
- AC
python

```
def solve(N, M, K, HS, CS, ABS):
    from collections import defaultdict
    edges = defaultdict(dict)
    for i in range(M):
        frm, to = ABS[i]
        frm -= 1
        to -= 1
        if HS[frm] < HS[to]:
            to, frm = frm, to
        # reversed edge
        edges[to][frm] = 1

    goal = N
    for c in CS:
        edges[goal][c - 1] = 0  # (1)

    distances = one_to_all(goal, N + 1, edges)
    INF = 9223372036854775807
    for i in range(N):
        d = distances[i]
        if d == INF:
            d = -1
        print(d)
```


---
This page is auto-translated from [/nishio/PAST5I](https://scrapbox.io/nishio/PAST5I) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
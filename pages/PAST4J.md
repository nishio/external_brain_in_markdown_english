---
title: "PAST4J"
---

from  [[Fourth Algorithm Practical Skills Test]]
PAST4J
[J - Warp](https://atcoder.jp/contests/past202010-open/tasks/past202010_j)
- Thoughts.
    - connected simple undirected graph
    - warp
    - The edge is 10^5, but if we explicitly make the warp an edge, we get 10^10
    - There must be a limit to the number of times you can use warp.
    - No, I can make it if I [[Dijkstra method]] in the priority queue.
    - We're not going to make it in time.
    - A few more considerations
        - Warp on the first move to a town of a different color than the start.
            - The same warp is never needed in subsequent explorations, the score is always bad.
            - Is the same true for return jumps?
        - No, answers don't match, hold.
    - Before modification, 31 TLE
    - 6WA, 1TLE after modification
        - Is it getting better?
        - What's wrong with using only one jump for each color?
            - Not one way, both ways.
    - Still, it's going to be 1 TLE.
        - quite so
        - When does that happen?
    - heapify collectively without heappush each time.
        - Oh, no.
        - Increased to 33 TLE.
    - Add visited
        - Passed through!
python

```
def solve(N, M, X, S, ABC):
    INF = 1e+99
    from collections import defaultdict
    edges = defaultdict(dict)
    for A, B, C in ABC:
        edges[A - 1][B - 1] = C
        edges[B - 1][A - 1] = C

    warps = [[], [], []]
    for i in range(N):
        warps[S[i]].append(i)

    usedWarp = set()
    GOAL = N - 1
    START = 0

    from heapq import heappush, heappop, heapify
    queue = [(0, START)]
    mincost = [INF] * N
    mincost[START] = 0
    visited = [0] * N

    while True:
        cost, pos = heappop(queue)
        if pos == GOAL:
            return cost
        if visited[pos]:
            continue
        visited[pos] = 1
        ep = edges[pos]
        for next in ep:
            nc = cost + ep[next]
            if nc < mincost[next]:
                mincost[next] = nc
                heappush(queue, (nc, next))

        for typ in range(3):
            if typ == S[pos]:
                continue
            warp = S[pos] + typ - 1

            if (S[pos], typ) in usedWarp:
                continue

            c = X[warp]
            usedWarp.add((S[pos], typ))

            nc = cost + c
            for next in warps[typ]:
                if nc < mincost[next]:
                    mincost[next] = nc
                    heappush(queue, (nc, next))
```



[https://twitter.com/maspy_stars/status/1325748032579645441?s=21](https://twitter.com/maspy_stars/status/1325748032579645441?s=21)
- [[arc061_c]]

---
This page is auto-translated from [/nishio/PAST4J](https://scrapbox.io/nishio/PAST4J) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
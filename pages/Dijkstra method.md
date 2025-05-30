---
title: "Dijkstra method"
---

- Algorithm for finding the shortest path
- The next step is to use [[priority queue]] to log order to find the vertices to be explored. [[heapq]].
    - O((E+V)log V)
    - [[anthology]]  p.96

python

```
def shortest_path(
        start, goal, num_vertexes, edges,
        INF=9223372036854775807, UNREACHABLE=-1):
    distances = [INF] * num_vertexes
    prev = [None] * num_vertexes
    distances[start] = 0
    queue = [(0, start)]
    while queue:
        d, frm = heappop(queue)
        if distances[frm] < d:
            # already know shorter path
            continue
        if frm == goal:
            path = [goal]
            p = goal
            while p != start:
                p = prev[p]
                path.append(p)
            path.reverse()
            return d, path
        for to in edges[frm]:
            new_cost = distances[frm] + edges[frm][to]
            if distances[to] > new_cost:
                # found shorter path
                distances[to] = new_cost
                prev[to] = frm
                heappush(queue, (distances[to], to))

    return UNREACHABLE
```

[https://judge.yosupo.jp/submission/28034](https://judge.yosupo.jp/submission/28034)

old version
- [Shortest Path](https://judge.yosupo.jp/problem/shortest_path)
    - [Submitted](https://judge.yosupo.jp/submission/13028)
python

```
from collections import defaultdict
from heapq import *
# fast input
import sys
input = sys.stdin.buffer.readline
INF = sys.maxsize

num_vertexes, num_edges, start, goal = map(int, input().split())

edges = defaultdict(dict)
distances = [INF] * num_vertexes
distances[start] = 0
shortest_path = defaultdict(list)
shortest_path[start] = []
for i in range(num_edges):
    a, b, c = map(int, input().split())
    edges[a][b] = c
    # edges[b][a] = c  # if bidirectional

queue = [(0, start)]
while queue:
    d, frm = heappop(queue)
    if distances[frm] < d:
        # already know shorter path
        continue
    if frm == goal:  # goal
        break
    for to in edges[frm]:
        if distances[to] > distances[frm] + edges[frm][to]:
            # found shorter path
            distances[to] = distances[frm] + edges[frm][to]
            heappush(queue, (distances[to], to))
            shortest_path[to] = (frm, to)

if distances[goal] == INF:
    # unreachable
    print(-1)
else:
    path = []
    cur = goal
    while True:
        frm, to = shortest_path[cur]
        path.append((frm, to))
        cur = frm
        if frm == start:
            break
    path.reverse()
    print(distances[goal], len(path))
    for frm, to in path:
        print(frm, to)
```

Modifications to this code
- Clarify where to discard the shortest path when it is not necessary to show the shortest path.
- Outputs the number of edges that make up a path, but often you want to sum the edge costs

---
This page is auto-translated from [/nishio/ダイクストラ法](https://scrapbox.io/nishio/ダイクストラ法) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
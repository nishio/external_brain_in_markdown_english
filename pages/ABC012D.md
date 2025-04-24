---
title: "ABC012D"
---

[D - Buses and the Inevitable Fate](https://atcoder.jp/contests/abc012/tasks/abc012_4)
- ![image](https://gyazo.com/ee05f83557e61f16cca327eded5de119/thumb/1000)
- Thoughts.
    - When the problem is to find the point that minimizes the distance to the farthest vertex, it is said to be a problem of finding the distance to the farthest vertex.
        - [[Graph Radius]] Right.
        - I think I was asking for it in the all wood DP.
            - I don't know if I can be asked such a difficult question with this level of difficulty.
            - Oh, this isn't a tree, is it?
        - O(V^3) in the [[Walsall-Floyd process]].
        - V is 300, so can you make it?
- Official Explanation
        - [[Dijkstra method]] Do O(V^2) V times or Warchalfroid
    - However, it has been verified that it does not work with slow languages such as Python.
    - Proposal to do Dijkstra with O((E+V)log V)
        - Let's try this.
    - Easily AC'd in Python.
        - 1.4 seconds at 5-second limit
        - I wonder if the judge machine has gotten faster since the issue was 6 years ago.
        - Or maybe by "verified not to pass" you mean the V^3 solution.
python

```
def solve(N, M, edges):
    INF = 9223372036854775807
    ret = INF

    for start in range(N):
        distances = [INF] * N
        distances[start] = 0
        queue = [(0, start)]
        while queue:
            d, frm = heappop(queue)
            if distances[frm] < d:
                # already know shorter path
                continue
            for to in edges[frm]:
                new_cost = distances[frm] + edges[frm][to]
                if distances[to] > new_cost:
                    # found shorter path
                    distances[to] = new_cost
                    heappush(queue, (distances[to], to))
        ret = min(ret, max(distances))
    return ret
```



---
This page is auto-translated from [/nishio/ABC012D](https://scrapbox.io/nishio/ABC012D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
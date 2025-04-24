---
title: "ABC190E"
---

from [[ABC190]]
ABC190E
[E - Magical Ornament](https://atcoder.jp/contests/abc190/tasks/abc190_e)[E - Magical Ornament](https://atcoder.jp/contests/abc190/tasks/abc190_e)
- ![image](https://gyazo.com/79456a6bfd6230660714426024778981/thumb/1000)
- Because of the constraint on the number of sides, I come up with [If the sides are 10^5, Dijkstra can use it.
- Since there are at most 17 vertices, we have to dijkstra 17 times to find the distance between the C vertices and the traveling salesman problem (the type that does not return to the starting point).
- Sample passed easily, but when submitted, 20AC 5WA 10TLE
    - That's tricky...
- Causes of WA
    - When making the unreachability determination, I was basing it on the inclusion of INF in Dijkstra's results.
    - It asks, "Is any vertex of the graph unreachable?" to determine if any vertex of the graph is unreachable.
    - If the C vertex is reachable, the other vertices don't matter.
- Time is running out with no one able to figure out how to solve the TLE.
- Official Explanation
    - BFS 17 times [[Shortest Hamilton Road Problem]].
    - Oh, so you're saying that if I had done BFS instead of Dijkstra, it would have gone through?
    - I tried and it went through...
python

```
def main():
    N, M = map(int, input().split())
    from collections import defaultdict
    edges = defaultdict(list)
    for _i in range(M):
        frm, to = map(int, input().split())
        edges[frm - 1].append(to - 1)  # -1 for 1-origin vertexes
        edges[to - 1].append(frm - 1)  # if bidirectional

    K = int(input())
    CS = list(int(x) - 1 for x in input().split())

    INF = 9223372036854775807
    dist = []
    for c in CS:
        d = one_to_all_bfs(c, N, edges, INF)
        dd = [d[CS[i]] for i in range(K)]
        if INF in dd:
            print(-1)
            return
        dist.append(dd)

    ret = tsp_not_return(K, dist)
    print(ret + 1)
```

    - The entire code is here [AC](https://atcoder.jp/contests/abc190/submissions/19822810)

---
This page is auto-translated from [/nishio/ABC190E](https://scrapbox.io/nishio/ABC190E) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
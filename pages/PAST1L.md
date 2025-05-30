---
title: "PAST1L"
---

[L - Gradient](https://atcoder.jp/contests/past201912-open/tasks/past201912_l)
![image](https://gyazo.com/622d3e70835a1497220daa46d7958222/thumb/1000)
- Thoughts.
    - Connect 30 vertices at the lowest cost
    - There are five auxiliary vertices that may or may not be connected.
    - That's nasty.
    - Find the minimum global tree with respect to "whether to pick 5 vertices" of 2^5?
        - Maybe we could start with the larger ones since removing the vertices won't improve the cost, but we'll get there in time without having to do that.
- Official Explanation
        - [[Steiner tree]] Issue.
        - But since T=30, [[Dreyfus-Wagner]] O(n 3^t + n^2 2^t + n^3) will not make it
        - [[minimum area tree]]
            - [[Kruskal method]]  O(E log E)
    - 35 vertices and about 10^3 edges, so there's plenty of time to search for all 2^5 patterns.
- 1WA
python

```
def solve(N, M, LARGE, SMALL):
    from math import sqrt
    edges = []
    for i in range(N):
        x1, y1, c1 = LARGE[i]
        for j in range(i + 1, N):
            x2, y2, c2 = LARGE[j]
            d = sqrt((x1 - x2) ** 2 + (y1 - y2) ** 2)
            if c1 != c2:
                d *= 10
            edges.append((d, i, j))
    large_edges = edges[:]

    INF = 9223372036854775807
    ret = INF
    for subset in range(2 ** M):
        edges = large_edges[:]
        for m in range(M):
            if subset & (1 << m):
                x2, y2, c2 = SMALL[m]
                for i in range(N):
                    x1, y1, c1 = LARGE[i]
                    d = sqrt((x1 - x2) ** 2 + (y1 - y2) ** 2)
                    if c1 != c2:
                        d *= 10
                    edges.append((d, i, N + m))

        init_unionfind(N + M)
        edges.sort()
        cost = 0
        for d, i, j in edges:
            if is_connected(i, j):
                continue
            unite(i, j)
            cost += d
        ret = min(ret, cost)
    return ret
```


[[PAST1L]]

---
This page is auto-translated from [/nishio/PAST1L](https://scrapbox.io/nishio/PAST1L) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
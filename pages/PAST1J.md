---
title: "PAST1J"
---

[J - Groundwork](https://atcoder.jp/contests/past201912-open/tasks/past201912_j)
- ![image](https://gyazo.com/35e2c2626e0ea16ae8009726cef684e2/thumb/1000)

- Thoughts.
    - Since there is a transit point, find the distance from the Y intersection to the three points and choose the one with the smallest sum.
    - The cost is on the vertices, not on the edges, but we can just search from the least expensive one in the [[Dijkstra method]] sense.
    - O(V^2logV), so we can make it in time.
- Official Explanation
        - [[Steiner tree]]
- AC
    - Construct a graph and use Dijkstra method to find one_to_all distances from three endpoints
    - This counts three intersections, so subtract two.
    - Answer the minimum cost of the Y-junction obtained
python

```
def solve(H, W, AS):
    from collections import defaultdict
    edges = defaultdict(dict)
    for x in range(W):
        for y in range(H):
            pos = y * W + x
            if x < W - 1:
                edges[pos + 1][pos] = AS[y][x]
            if x > 0:
                edges[pos - 1][pos] = AS[y][x]
            if y < H - 1:
                edges[pos + W][pos] = AS[y][x]
            if y > 0:
                edges[pos - W][pos] = AS[y][x]
    d1 = one_to_all(W - 1, H * W, edges)
    d2 = one_to_all(W * (H - 1), H * W, edges)
    d3 = one_to_all(W * H - 1, H * W, edges)
    INF = 9223372036854775807
    ret = INF
    for x in range(W):
        for y in range(H):
            pos = y * W + x
            v = d1[pos] + d2[pos] + d3[pos] - 2 * AS[y][x]
            if v < ret:
                ret = v

    return ret
```


    - [[shortest path problem]]
    - [[Shortest path not a straight road]]

- [[First Algorithm Practical Skills Test]]

---
This page is auto-translated from [/nishio/PAST1J](https://scrapbox.io/nishio/PAST1J) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
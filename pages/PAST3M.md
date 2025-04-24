---
title: "PAST3M"
---

![image](https://gyazo.com/03933bba41c9b05e4ac79210321a5771/thumb/1000)
[M - Peddling Plan Problem](https://atcoder.jp/contests/past202005-open/tasks/past202005_m)

from  [[Third Algorithm Practical Skills Test]]
PAST3M
- Thoughts.
    - At first glance, [[TSP]] but with so many vertices, could a more efficient algorithm be used?
    - Characteristic problem conditions
        - Constant edge cost
        - You can use the same vertex or edge over and over.
        - The sides are held back by 10^5.
        - Is [[minimum area tree]] the minimum cost?
        - Different. For example, when going around 4 vertices, if s is in the center of the Y, cost 5, if s is at the end of the path, cost 3
    - Is it a tree?
        - Maybe so...
- Problem Condition Overlooked
    - Instead of going around N cities, they were going around K cities.
    - Traveling salesman problem to find the distance between each of the K vertices first?
- think again
    - K is as high as 16
        - 16! cannot be searched in its entirety.
        - If it's a product of 2^16 cities already visited and 16 cities last visited, it's fine.
        - →[[bitDP]]
    - Vertex is 10^5
            - [[Walsall-Floyd process]] O(V^3) is impossible
        - The sides are held back by 10^5.
        - Thanks to this constraint, we can use [[Dijkstra method]] O((E+V)log V)
                - [[If the sides are 10^5, Dijkstra can use it.]]
    - Find the one to all shortest distance from 16 vertices with Dijkstra
    - Traveling salesman problem based on distances between 16 vertices
        - Note that the pattern does not return to the start
- AC
python

```
def solve(N, M, edges, S, K, TS):
    cc = CoordinateCompression(TS)
    v2i, _i2v = cc.compress()

    # dijkstra
    from collections import defaultdict
    distances = defaultdict(dict)
    ds = one_to_all(S, N, edges)
    from_start = {}
    for t in TS:
        from_start[v2i[t]] = ds[t]

    for t in TS:
        ds = one_to_all(t, N, edges)
        for t2 in TS:
            distances[v2i[t]][v2i[t2]] = ds[t2]

    # tsp
    num_vertex = K
    SUBSETS = 2 ** num_vertex
    INF = 9223372036854775807
    memo = [[INF] * num_vertex for _s in range(SUBSETS)]

    for subset in range(1, SUBSETS):
        for v in range(num_vertex):  # new vertex
            mask = 1 << v
            if subset == 1 << v:
                # previous vertex is start
                memo[subset][v] = min(
                    memo[subset][v],
                    from_start[v])
            elif subset & mask:  # new subset includes v
                for u in range(num_vertex):
                    memo[subset][v] = min(
                        memo[subset][v],
                        memo[subset ^ mask][u] + distances[u][v])
    return min(memo[-1])
```


- [[Constraints with 10^5 edges]]

---
This page is auto-translated from [/nishio/PAST3M](https://scrapbox.io/nishio/PAST3M) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
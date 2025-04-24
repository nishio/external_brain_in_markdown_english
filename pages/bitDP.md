---
title: "bitDP"
---

An implementation technique for doing [[dynamic programming]] with sets as the domain. $O(N2^N)$. N=24 is about $4\times 10^8$.

Before computing a value for a set S, we want the value for a set S with one element removed from it to be determined.
In other words, I want to topologically sort a graph that considers the relation "one element removed" as a directed edge and compute it in that order.
If we map "contains element i" of the set to "the i-th bit is 1" of the integers, then the natural ordering of the integers is also the topological sorting of the graph.

As `mask = 1 << i`.
- $i \in S$: `S & mask`
    - At that time $S / i$: `S ^ mask`.

Example: [[TSP]] $m(S,v) = \min_{u \in S} \{ m(S / u, u) + d(u, v) \}$
python

```
def solve_tsp(num_vertex, distance):
    import sys
    INF = sys.maxsize

    SIZE = 2 ** num_vertex
    memo = [[INF] * num_vertex for _i in range(SIZE)]

    memo[0][0] = 0
    for subset in range(1, SIZE):
        for v in range(num_vertex):
            for u in range(num_vertex):
                mask = 1 << u
                if subset & mask:
                    memo[subset][v] = min(
                        memo[subset][v],
                        memo[subset ^ mask][u] + distance[u][v])
    return memo[-1][0]
```


---
This page is auto-translated from [/nishio/bitDP](https://scrapbox.io/nishio/bitDP) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
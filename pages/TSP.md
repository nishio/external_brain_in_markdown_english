---
title: "TSP"
---

O(x^2 2^x)
- [[bit DP]]
    - Towns already visited 2^x
    - Last town visited x
    - Next town to visit x

Some patterns return to the starting point and some do not.
- [[ABC180E]]: Back
- [[PAST3M]]: not back

python

```
def tsp_return(num_vertex, distances):
    # ABC180E
    INF = 9223372036854775807
    SUBSETS = 2 ** num_vertex
    memo = [[INF] * num_vertex for _i in range(SUBSETS)]

    memo[0][0] = 0
    for subset in range(1, SUBSETS):
        for v in range(num_vertex):
            for u in range(num_vertex):
                mask = 1 << u
                if subset & mask:
                    memo[subset][v] = min(
                        memo[subset][v],
                        memo[subset ^ mask][u] + distances[u][v])
    return memo[-1][0]


def tsp_not_return(num_vertex, distances, from_start):
    # PAST3M
    INF = 9223372036854775807
    SUBSETS = 2 ** num_vertex
    memo = [[INF] * num_vertex for _i in range(SUBSETS)]

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



---
This page is auto-translated from [/nishio/巡回セールスマン問題](https://scrapbox.io/nishio/巡回セールスマン問題) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "ABC180E"
---

from [[ABC180]]
[E - Traveling Salesman among Aerial Cities](https://atcoder.jp/contests/abc180/tasks/abc180_e)
- ![image](https://gyazo.com/f3e649bb12de0bbd15495e3c67a3523e/thumb/1000)
- Thoughts.
    - 17 factorial is large enough.
        - Problems solving [[TSP]] ([[TSP]]) with [bitDP
    - Is the "may pass through the same city twice" in Sample 2 a little different?
        - But I don't see a pattern where it would be beneficial to go through another city instead of moving directly.
    - I'll refer you to an article on solving the traveling salesman problem with bitDP by googling the appropriate article.
        - [[[Competitive Pro]] Introduction to bitDP (for green and water coders) - Qiita []](https://qiita.com/xryuseix/items/7ca1aec4b1a7e8bff997)
    - Needs a slight correction as it is "until you return to city 1" not "until you visit all cities from city 1."
    - Fixed and small sample passes, but large sample doesn't. Contest ends without finding the cause.
- after the contest
    - Bring in an implementation of someone doing AC and make a small sample of the random input that causes discrepancies.
    - `5, [[1, 1, 0], [1, 2, 1], [1, 1, 1], [1, 2, 0], [2, 0, 1]]` returns 8 when it is really 7
    - I looked at [[anthology]] and found the code for TSP in the case of a loop, so I referred to it and easily AC'd it in 26 minutes.
python

```
def solve(N, XYZS):
    import sys
    INF = sys.maxsize  # float("inf")

    dist = []
    for i in range(N):
        a, b, c = XYZS[i]
        ds = []
        dist.append(ds)
        for j in range(N):
            p, q, r = XYZS[j]
            ds.append(abs(p - a) + abs(q - b) + max(0, r - c))

    SIZE = 2 ** N
    memo = [[INF] * N for _i in range(SIZE)]
    memo[-1][0] = 0
    for subset in range(SIZE - 2, -1, -1):
        for v in range(N):
            for u in range(N):
                if (subset >> u) & 1 == 0:
                    mask = 1 << u
                    memo[subset][v] = min(
                        memo[subset][v],
                        memo[subset | mask][u] + dist[v][u]
                    )
    return memo[0][0]
```

- consideration
    - The Qiita one has the final vertex for each subset as an array last value.
    - I have the ant book with the subscripts.
    - The Qiita one doesn't include the path back to vertex 0 because the problem condition is "the shortest path that starts at vertex 0 and follows all vertices".
        - Even if this algorithm finds the shortest path, the way back from it may be expensive
    - This issue and the ant book example are the shortest closed path
        - So the problem conditions are fundamentally different from Qiita's explanation.
    - Commentary on the side of the ant book
        - Start at vertex 0, but do not initially include vertex 0 when considering the visited vertex set
        - In this way, when the "visited vertex set becomes the whole set", it means "returned to vertex 0", so it can be applied to the problem condition including the return path
        - Is there any deeper meaning in having DPs in reverse order?
            - It works fine in the correct order, so there doesn't seem to be a deep meaning.
python

```
    memo[0][0] = 0
    for subset in range(1, SIZE):
        for v in range(N):
            for u in range(N):
                mask = 1 << u
                if subset & mask:
                    memo[subset][v] = min(
                        memo[subset][v],
                        memo[subset ^ mask][u] + dist[u][v])
    return memo[-1][0]
```



---
This page is auto-translated from [/nishio/ABC180E](https://scrapbox.io/nishio/ABC180E) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
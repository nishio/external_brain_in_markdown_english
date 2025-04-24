---
title: "DP B"
---

from  [[dynamic programming]]
DP_B
First, [[DP to be distributed]].
python

```
def solve(N, K, heights):
    heights += [INF] * K
    costs = [INF] * (N + K)
    costs[0] = 0
    for i in range(N - 1):
        for k in range(1, K + 1):
            costs[i + k] = min(
                costs[i + k],
                costs[i] + abs(heights[i + k] - heights[i]))
    return costs[N - 1]
```


However, 3TLE.
I removed the function call as follows, but 1 TLE remained
I was thinking of compiling it in Numba.
Submitted by PyPy, 165msec AC

python

```
def solve(N, K, heights):
    heights += [INF] * K
    costs = [INF] * (N + K)
    costs[0] = 0
    for i in range(N - 1):
        for k in range(1, K + 1):
            newcost = costs[i] + abs(heights[i + k] - heights[i])
            if newcost < costs[i + k]:
                costs[i + k] = newcost
    return costs[N - 1]
```


- [[Collecting DP]] 、
- 1625 ms AC
- PyPy 385 ms
python

```
def solve(N, K, heights):
    costs = [0] * N
    costs[0] = 0
    for i in range(1, N):
        costs[i] = min(
            costs[j] + abs(heights[i] - heights[j])
            for j in range(max(i - K, 0), i)
        )
```


- 8TLE
- PyPy 540 ms AC
python

```
def solve(N, K, heights):
    costs = [None] * N
    costs[0] = 0

    def get_cost(i):
        if costs[i] != None:
            return costs[i]

        c = min(
            get_cost(j) + abs(heights[i] - heights[j])
            for j in range(max(i - K, 0), i)
        )
        costs[i] = c
        return c

    return get_cost(N - 1)
```


---
This page is auto-translated from [/nishio/DP B](https://scrapbox.io/nishio/DP B) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
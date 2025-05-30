---
title: "DP A"
---

[A - Frog 1](https://atcoder.jp/contests/dp/tasks/dp_a)
- Going from start to finish
- At each point, there are two options to proceed one or two steps forward, with different costs
- The problem of finding the minimum cost to reach the goal
- Let each point be the domain of definition and the minimum cost to get there be the value DP

from  [[dynamic programming]]
DP_A
Anyway, I kind of wrote it down and it was [[Collecting DP]].
python

```
def solve(N, heights):
    costs = [0] * N
    costs[0] = 0
    costs[1] = abs(heights[1] - heights[0])
    for i in range(2, N):
        costs[i] = min(
            costs[i - 2] + abs(heights[i] - heights[i - 2]),
            costs[i - 1] + abs(heights[i] - heights[i - 1]),
        )
    return costs[-1]
```


I dared to write this in [[DP to be distributed]].
- Because of the way it is written, "choose the smaller of the current value and the new value," it is initialized with a sufficiently large value INF.
- Actually, for this problem, the second min always has the smallest new value and is always updated first, so we can eliminate this min and not initialize the cost
- I needed to reserve one larger to avoid out-of-range accesses because i needed to run just before the goal, but it references two ahead of it.
    - The equivalent is handled in the form of "pre-calculating 0s and 1s" and "starting the loop from 2" in the DP to be collected.
- Personally, I feel like I need to twist my head a bit
python

```
def solve(N, heights):
    heights += [INF]
    costs = [INF] * (N + 1)
    costs[0] = 0
    for i in range(N - 1):
        costs[i + 1] = min(
            costs[i + 1],
            costs[i] + abs(heights[i + 1] - heights[i]))
        costs[i + 2] = min(
            costs[i + 2],
            costs[i] + abs(heights[i + 2] - heights[i]))
    return costs[N - 1]
```


- Written by [memory recursion
- this is an honest
- Which values have been calculated is pushed to the memoizing section, and humans don't care.
- It must be possible to identify if it has been calculated or not, so it is initialized with an impossible value (None) as a cost.
python

```
def solve(N, heights):
    costs = [None] * N
    costs[0] = 0
    costs[1] = abs(heights[1] - heights[0])

    def get_cost(i):
        if costs[i] != None:
            return costs[i]

        c = min(
            get_cost(i - 2) + abs(heights[i] - heights[i - 2]),
            get_cost(i - 1) + abs(heights[i] - heights[i - 1]),
        )
        costs[i] = c
        return c

    return get_cost(N - 1)
```


---
This page is auto-translated from [/nishio/DP A](https://scrapbox.io/nishio/DP A) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
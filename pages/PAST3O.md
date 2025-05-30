---
title: "PAST3O"
---

![image](https://gyazo.com/c243561fb3069ff0f7a2c41046325ef2/thumb/1000)


from  [[Third Algorithm Practical Skills Test]]
PAST3O
![image](https://gyazo.com/44f1480ffab9934faa88f95412112586/thumb/1000)
[O - Ring Toss](https://atcoder.jp/contests/past202005-open/tasks/past202005_o)
- Thoughts.
        - Do [[Choose M from N]] three times
- Official Explanation
        - [[least-cost current]]
    - It is important that the incremental cost at times 1, 2, and 3 be monotonically increasing
    - Three sides can be subtracted.
    - ![image](https://gyazo.com/9e4af4847d4cf7c78354a6753ac9b49c/thumb/1000)
    - ![image](https://gyazo.com/c243561fb3069ff0f7a2c41046325ef2/thumb/1000)

    - I look at the problem and attribute it to the least cost flow, what should I think about...
            - [[Attributed to the least-cost stream]] Made
- AC
    - Graph Construction
        - Mistakes with subscripts
        - Negative edges sometimes return incorrect values, so add INF.
python

```
def solve(N, M, AS, BS, RS):
    INF = 10 ** 5
    mcf = MinCostFlow(N + 5)
    start = N
    goal = N + 1
    round = N + 2
    for i in range(3):
        mcf.add_edge(start, round + i, M, 0)

    for i in range(3):
        for j in range(N):
            r = AS[j] * (BS[j] ** (i + 1)) % RS[i]
            mcf.add_edge(round + i, j, 1, INF - r)

    for j in range(N):
        cs = [AS[j] * (BS[j] ** (k + 1)) for k in range(3)]
        cs.append(0)
        for k in range(3):
            c = cs[k] - cs[k-1]
            mcf.add_edge(j, goal, 1, c)

    return INF * (3 * M) - mcf.flow(start, goal)[-1]
```



---
This page is auto-translated from [/nishio/PAST3O](https://scrapbox.io/nishio/PAST3O) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
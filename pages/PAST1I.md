---
title: "PAST1I"
---

[I - Parts Procurement](https://atcoder.jp/contests/past201912-open/tasks/past201912_i)
- ![image](https://gyazo.com/c2448c08a7e7e39a1cf0cef3c676a36a/thumb/1000)
- Thoughts.
    - The problem of matching 10 parts with minimum cost by choosing some from a set of 1000 parts.
    - 2^1000 is too big, but 1000 x 2^10 is about 10^6, so there is plenty of room
    - DP with the 2^10 subset as the definition domain and the minimum cost to achieve it as the value domain.
    - Initialize the empty set with 0 and others with INF and chmin for each set
- Official Explanation OK
- AC
python

```
def solve(N, M, SS, CS):
    INF = 9223372036854775807
    table = [INF] * (2 ** N)
    table[0] = 0
    SS = [int(s.replace("Y", "1").replace("N", "0"), 2) for s in SS]
    for i in range(M):
        s = SS[i]
        for src in range(2 ** N):
            dst = s | src
            table[dst] = min(table[dst], table[src] + CS[i])
    ret = table[2 ** N - 1]
    if ret == INF:
        return -1
    return ret
```


- [[bit DP]]
    - [[Cost minimization]]

- [[First Algorithm Practical Skills Test]]
---
This page is auto-translated from [/nishio/PAST1I](https://scrapbox.io/nishio/PAST1I) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
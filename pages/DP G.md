---
title: "DP G"
---

from  [[dynamic programming]]
DP_G
G
- The problem of finding the longest path in a graph

[[DP_G bad]]

1TLE
python

```
def solve(N, M, edges):
    longest = [-1] * (N + 1)

    def get_longest(start):
        if longest[start] != -1:
            return longest[start]

        next_edges = edges.get(start)
        if not next_edges:
            ret = 0
        else:
            ret = max(get_longest(v) for v in edges[start]) + 1
        longest[start] = ret
        return ret

    return max(get_longest(v) for v in edges)
```


Python 428 ms AC
python

```
def solve(N, M, edges):
    longest = [-1] * (N + 1)
 
    for i in range(N + 1):
        if not edges[i]:
            longest[i] = 0
 
    def get_longest(start):
        next = edges[start]
        for v in next:
            if longest[v] == -1:
                longest[v] = get_longest(v)
 
        ret = max(longest[v] for v in next) + 1
        return ret
 
    for i in range(N + 1):
        if longest[i] == -1:
            longest[i] = get_longest(i)
 
    return max(longest[v] for v in edges)
```


Cython
- [https://atcoder.jp/contests/dp/submissions/14906046](https://atcoder.jp/contests/dp/submissions/14906046)

---
This page is auto-translated from [/nishio/DP G](https://scrapbox.io/nishio/DP G) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
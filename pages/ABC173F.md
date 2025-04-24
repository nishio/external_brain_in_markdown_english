---
title: "ABC173F"
---

- Tree has exactly the number of vertices - 1 edge
- Therefore, the number of trees in the forest is obtained from the number of vertices v and the number of edges e
    - $f(L,R) = v(L,R) - e(L,R)$
        - [Number of connected components in Graphs without closed paths
    - [[Change order of operations]]
    - $\sum_L \sum_R f(L,R) = \sum_L \sum_R v(L,R) - \sum_L \sum_R e(L,R)$
    - $\sum_L \sum_R 1_{L \le i \le R}  = (N - (i-1)) ((i-1) + 1)$

python

```
def main():
    v = 0
    e = 0
    N = int(input())
    for i in range(N):
        v += (N - i) * (i + 1)

    for i in range(N - 1):
        v1, v2 = sorted(map(int, input().split()))
        v1 -= 1
        v2 -= 1
        e += (N - v2) * (v1 + 1)

    debug(": e, v", e, v)
    print(v - e)
```


[https://atcoder.jp/contests/abc173/submissions/15029754](https://atcoder.jp/contests/abc173/submissions/15029754)

---
This page is auto-translated from [/nishio/ABC173F](https://scrapbox.io/nishio/ABC173F) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
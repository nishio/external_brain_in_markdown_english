---
title: "abc040_c"
---

Problem seen in [[DP A]]. The same solution is not interesting, so I tried "dynamic programming but not allocating the array" and RE'd it when the column length was short.
[C - Pillar Pillar Pillar Pillar](https://atcoder.jp/contests/abc040/tasks/abc040_c)
python

```
def solve(N, XS):
    if N == 1:
        return 0
    a = abs(XS[1] - XS[0])
    if N == 2:
        return a
    b = abs(XS[2] - XS[0])
    if N == 3:
        return b
    for i in range(3, N):
        v = min(
            a + abs(XS[i - 2] - XS[i]),
            b + abs(XS[i - 1] - XS[i]),
        )
        a = b
        b = v
    return v
```


[https://atcoder.jp/contests/abc040/submissions/15212600](https://atcoder.jp/contests/abc040/submissions/15212600)

---
This page is auto-translated from [/nishio/abc040_c](https://scrapbox.io/nishio/abc040_c) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Static Range Sum"
---

- [Static Range Sum](https://judge.yosupo.jp/problem/static_range_sum)
- [[itertools.accumulate]] [[itertools]]
    - [[cumulative sum]]
python

```
from itertools import accumulate
N, Q = map(int, input().split())
AS = list(map(int, input().split()))
AS.append(0)
sums = list(accumulate(AS))
for q in range(Q):
    L, R = map(int, input().split())
    s = sums[R - 1]
    if L > 0:
        s -= sums[L - 1]
    print(s)
```

[https://judge.yosupo.jp/submission/13009](https://judge.yosupo.jp/submission/13009)

[[atcoder]]

---
This page is auto-translated from [/nishio/Static Range Sum](https://scrapbox.io/nishio/Static Range Sum) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
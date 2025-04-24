---
title: "PAST4H"
---

from  [[Fourth Algorithm Practical Skills Test]]
PAST4H
[H - Mass Cutting](https://atcoder.jp/contests/past202010-open/tasks/past202010_h)
- Thoughts.
    - 900 in the high 900's
        - And 900 more to spare.
    - Let's explore all of them naively.
        - Try the smaller ones, and if they don't work, try the larger ones.
python

```
def solve(N, M, K, data):
    from collections import Counter
    ret = 1
    for y in range(N):
        for x in range(M):
            for w in range(ret + 1, min(N - y + 1, M - x + 1)):
                c = Counter(data[y + i][x + j]
                            for i in range(w)
                            for j in range(w))

                mc = c.most_common(1)[0][1]
                if mc + K >= w * w:
                    ret = w

    return ret
```


---
This page is auto-translated from [/nishio/PAST4H](https://scrapbox.io/nishio/PAST4H) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
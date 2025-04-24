---
title: "PAST4F"
---

from  [[Fourth Algorithm Practical Skills Test]]
PAST4F
[F - Parsing](https://atcoder.jp/contests/past202010-open/tasks/past202010_f)
- AMBIGUOUS if the number of occurrences is the same compared to above or below.
python

```
def solve(N, K, SS):
    from collections import Counter
    c = Counter(SS).most_common()
    K -= 1
    ck, ckv = c[K]
    if K > 0:
        _, pv = c[K - 1]
        if pv == ckv:
            return "AMBIGUOUS"
    if K < len(c) - 1:
        _, pv = c[K + 1]
        if pv == ckv:
            return "AMBIGUOUS"
    return ck
```


---
This page is auto-translated from [/nishio/PAST4F](https://scrapbox.io/nishio/PAST4F) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
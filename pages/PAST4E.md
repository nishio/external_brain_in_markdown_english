---
title: "PAST4E"
---

from  [[Fourth Algorithm Practical Skills Test]]
PAST4E
[E - Anagrams](https://atcoder.jp/contests/past202010-open/tasks/past202010_e)
- Thoughts.
    - 5 so all search
python

```
def solve(N, S):
    from itertools import permutations
    rS = "".join(reversed(S))
    for p in permutations(S):
        ret = "".join(p)
        if ret != S and ret != rS:
            return ret
    return "None"
```


---
This page is auto-translated from [/nishio/PAST4E](https://scrapbox.io/nishio/PAST4E) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
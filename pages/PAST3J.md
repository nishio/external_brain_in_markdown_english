---
title: "PAST3J"
---

from  [[Third Algorithm Practical Skills Test]]
PAST3J
- The question to answer who takes which number when there are several agents in a row who only take it when the number flowing in is greater than any of those they have taken so far.
- Each agent has a numerical value that it will take if it is greater than this, and it should return "the leftmost agent with a value less than the flowing numerical value x".
    - So this is an efficient search from a sorted array.
    - I looked up the bisect search method in Python and found [[bisect]] in the standard library, so I used it for the first time.
python

```
from bisect import bisect_right
N, M = [int(x) for x in input().split()]
XS = [int(x) for x in input().split()]

scores = [0] * N

for x in XS:
    # need to nagate to keep asc. order
    # print("come", x)
    i = bisect_right(scores, -x)
    if i == N:
        print(-1)
    else:
        print(i + 1)
        scores[i] = -x
        # print(scores)
```


---
This page is auto-translated from [/nishio/PAST3J](https://scrapbox.io/nishio/PAST3J) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
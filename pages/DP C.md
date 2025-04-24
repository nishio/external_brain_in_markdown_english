---
title: "DP C"
---

[C - Vacation](https://atcoder.jp/contests/dp/tasks/dp_c)
- I want to take the greatest sum from three sequences of numbers.
- However, they cannot be taken consecutively from the same sequence of numbers.
- The defining region is which of the three ways was the immediate previous one, and the value is the sum of the three cases.
from  [[dynamic programming]]
DP_C
- PyPy 144 ms
python

```
def solve(N, scores):
    last_score = scores[0]
    for i in range(1, N):
        next_score = [
            max(last_score[1], last_score[2]) + scores[i][0],
            max(last_score[2], last_score[0]) + scores[i][1],
            max(last_score[0], last_score[1]) + scores[i][2],
        ]
        last_score = next_score
    return max(last_score)
```


---
This page is auto-translated from [/nishio/DP C](https://scrapbox.io/nishio/DP C) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
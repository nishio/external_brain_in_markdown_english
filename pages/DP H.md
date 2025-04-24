---
title: "DP H"
---

[H - Grid 1](https://atcoder.jp/contests/dp/tasks/dp_h)
- An obstacle is placed on the grid, the question is how many paths are there from the upper left to the lower right by moving right or down?
    - [[routing count]]
- A point on the grid is the domain, and the number of paths to that point is the DP value.
from  [[dynamic programming]]
DP_H
H:

python

```
def solve(H, W, data):
    score = [[0] * (W + 1) for i in range(H + 1)]
    score[0][1] = 1
    for y in range(1, H + 1):
        for x in range(1, W + 1):
            if data[y - 1][x - 1] == ord("#"):
                score[y][x] = 0
            else:
                score[y][x] = (score[y - 1][x] + score[y][x - 1]) % MOD
    return score[H][W]
```


---
This page is auto-translated from [/nishio/DP H](https://scrapbox.io/nishio/DP H) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
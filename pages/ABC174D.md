---
title: "ABC174D"
---

![image](https://gyazo.com/2b5229aa9bfb5bab165b982e0641755a/thumb/1000)
from [[ABC174]]
ABC174D
D - Alter Altar []](https://atcoder.jp/contests/abc174/tasks/abc174_d)
- ![image](https://gyazo.com/473d4f6d9bda62df85a8ed87e2d02976/thumb/1000)
- You want to avoid including WR, which in essence means you want to R*W*.
- If you look at it from the far right and far left, and replace the stones that are breaking the rules, the extent to which the rules are being followed will monotonically increase.
    - ![image](https://gyazo.com/2b5229aa9bfb5bab165b982e0641755a/thumb/1000)

    - No color change required.
    - If the color change is valid, then the replacement of the target stone is equally valid (miscellaneous).
        - ![image](https://gyazo.com/e3b8e85a6e2080078ea6e10bcd15fb5c/thumb/1000)
    - A slightly more sane explanation
        - Consider the given columns rearranged to satisfy the condition
        - The number of discrepancies of the current column with that column is called the cost
        - The above replacement operation always reduces the cost by 2
        - Color change reduces cost by 1 and moves one red castle boundary.
            - If the stone whose affiliation has been changed due to the boundary move is of the correct color, the cost is reduced by an additional 1, but if not, the cost is increased by 1.
        - Thus, the color change reduces the cost by a maximum value of 2. This is as efficient or less efficient than replacement.
python

```
def solve(N, CS):
    left = 0
    right = N - 1
    R = ord("R")
    W = ord("W")
    ret = 0
    while left < right:
        if CS[left] == R:
            left += 1
            continue
        if CS[right] == W:
            right -= 1
            continue
        # swap
        left += 1
        right -= 1
        ret += 1
    return ret
```


---
This page is auto-translated from [/nishio/ABC174D](https://scrapbox.io/nishio/ABC174D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
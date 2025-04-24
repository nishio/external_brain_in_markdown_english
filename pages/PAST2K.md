---
title: "PAST2K"
---

from  [[Second Algorithm Practical Skills Test]]
PAST2K
- Thoughts.
    - The issue of changing and deleting to make corresponding parentheses.
    - Conversion and deletion costs are fixed for each character.
    - N=3000
    - There is no advantage in converting and then deleting, so there are three options: do nothing, convert, or delete.
    - If we set the parentheses as plamy 1 and the deletion as 0, we could make a DP with Y as the "sum up to the Xth".
        - Corresponding parentheses are non-negative in the middle and zero at the end
        - Values range from 0 to N
        - N^2, so it's not too late.
- AC
python

```
def solve(N, S, CS, DS):
    INF = 9223372036854775807
    table = [INF] * (N + 1)  # table[N] is sentinel
    table[0] = 0
    for i in range(N):
        new_table = [INF] * (N + 1)
        if S[i] == "(":
            d = 1
        else:
            d = -1

        for j in range(N):
            new_table[j] = min(
                table[j - d],  # no change
                table[j + d] + CS[i],  # change
                table[j] + DS[i],  # delete
            )
        table = new_table
    return table[0]
```


    - [[Bracketed rows are up and down]]
    - [[dynamic programming]]
    - [[Watchdogs up and down the range]]

---
This page is auto-translated from [/nishio/PAST2K](https://scrapbox.io/nishio/PAST2K) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "DP K"
---

[K - Stones](https://atcoder.jp/contests/dp/tasks/dp_k)
- Competitive Game Read-Out Issues
- DP with the board as the domain of definition
    - The board can be represented by a single integer.
    - The value is "the person who is handed the board wins or loses."
    - Tracing backwards from the end of the game where there is nothing left to take and you lose.
            - [[time reversal (physics)]]
python

```
def solve(N, K, AS):
    AS.sort()
    MIN = AS[0]
 
    table = [0] * (K + 1)
    for i in range(MIN):
        table[i] = -1  # LOSE
 
    for i in range(MIN, K + 1):
        for a in AS:
            if table[i - a] == -1:
                table[i] = 1
                break
        else:
            table[i] = -1
 
    # debug(": table", table)
 
    if table[K] == 1:
        return "First"
 
    else:
        return "Second"
```

[https://atcoder.jp/contests/dp/submissions/15052948](https://atcoder.jp/contests/dp/submissions/15052948)

---
This page is auto-translated from [/nishio/DP K](https://scrapbox.io/nishio/DP K) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
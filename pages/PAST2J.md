---
title: "PAST2J"
---

from  [[Second Algorithm Practical Skills Test]]
![image](https://gyazo.com/b4d2ae6d4c49a41f64ced937f0f5dbae/thumb/1000)
[J - string parsing](https://atcoder.jp/contests/past202004-open/tasks/past202004_j)

PAST2J
- We can call it recursively with a function that handles the range enclosed by the parentheses.
- Access strings by subscripts instead of editing them directly
- AC
python

```
def solve(S):
    N = len(S)
    cur = 0
    ret = []

    def parse_palen():
        nonlocal cur
        cur += 1
        ret = []
        while cur < N:
            c = S[cur]
            if c == ")":
                s = "".join(ret)
                s2 = "".join(reversed(s))
                return s + s2
            elif c == "(":
                ret.append(parse_palen())
            else:
                ret.append(c)
            cur += 1

    while cur < N:
        c = S[cur]
        if c == "(":
            ret.append(parse_palen())
        else:
            ret.append(c)
        cur += 1
    return "".join(ret)
```


9min

---
This page is auto-translated from [/nishio/PAST2J](https://scrapbox.io/nishio/PAST2J) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
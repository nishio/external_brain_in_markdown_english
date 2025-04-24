---
title: "ARC110C"
---

from [[ARC110]]
Issues related to [C - Exoswap](https://atcoder.jp/contests/arc110/tasks/arc110_c) [ARC110F
![image](https://gyazo.com/f71976b9a1f12a846b3cf359703b0135/thumb/1000)

ARC110C
- Do it greedily
- Think "How to bring one to the front of the line?"
    - It is essential to have a replacement that brings you from where you are now to the front of the line.
- If there is an excess or deficiency, it is NG.
- Related: [[Greed Law Proof Patterns]].
python

```
def solve(N, PS):
    ret = []
    used = [False] * (N - 1)

    def swap(x):
        PS[x - 1], PS[x] = PS[x], PS[x - 1]
        used[x - 1] = True
        ret.append(x)

    for target in range(1, N):
        x = PS.index(target, target - 1)
        for i in range(x, target - 1, -1):
            if used[i - 1]:
                return [-1]
            swap(i)

    if False in used:
        return [-1]
    return ret
```


---
This page is auto-translated from [/nishio/ARC110C](https://scrapbox.io/nishio/ARC110C) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
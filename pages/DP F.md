---
title: "DP F"
---

from  [[dynamic programming]]
DP_F
    - [[longest substring]] 　[[LCS]]
- I did np.zeros where I made a two-dimensional array filled with zeros, but in raw Python it's TLE, so I made a raw list and then PyPy'd it.
- chr is doing this to change the characters back to a string since they are integer values when buffer.read is done.
python

```
def solve(S, T):
    sizeS = len(S)
    sizeT = len(T)
    m = [[0] * (sizeT + 1) for _i in range(sizeS + 1)]
    for i in range(1, sizeS + 1):
        for j in range(1, sizeT + 1):
            m[i][j] = max(
                m[i - 1][j],
                m[i][j - 1],
                m[i - 1][j - 1] + 1 if S[i - 1] == T[j - 1] else 0
            )
    result = []
    i = sizeS
    j = sizeT
    while i > 0 and j > 0:
        if m[i][j] == m[i - 1][j]:
            i -= 1
        elif m[i][j] == m[i][j - 1]:
            j -= 1
        else:
            result.append(chr(S[i - 1]))
            i -= 1
            j -= 1
    print("".join(reversed(result)))
```


---
This page is auto-translated from [/nishio/DP F](https://scrapbox.io/nishio/DP F) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "PAST3F"
---

from  [[Third Algorithm Practical Skills Test]]
PAST3F
F The problem is to determine if [[palindrome]] can be created from the given character candidates, and if so, to output one of them. The "pair of the Nth character from the front and the Nth character from the back" is independent of the other N characters, so it can be considered separately. If the common subset of the candidates is empty, there is no solution. If there is a common subset, choose one at random. The final process should be divided according to whether the length is even or odd.
python

```
N = int(input())
M = []
for i in range(N):
    M.append(input())

answer = []
for i in range(N // 2):
    ok_chars = set(M[i]).intersection(M[N - 1 - i])
    if not ok_chars:
        print(-1)
        break
    answer.append(list(ok_chars)[0])
else:
    if N % 2 == 0:
        print("".join(answer) + "".join(reversed(answer)))
    else:
        print("".join(answer) + M[N//2][0] + "".join(reversed(answer)))
```


---
This page is auto-translated from [/nishio/PAST3F](https://scrapbox.io/nishio/PAST3F) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
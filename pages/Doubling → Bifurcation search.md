---
title: "Doubling → Bifurcation search"
---

- When [[dichotomous search]] is performed on [[doubling]] results, it is simpler and faster to make the code tightly coupled than to think of them as separate parts.

python 

```
# find x s.t. f(x) = y
x = 0
for i in range(30 - 1, -1, -1):
    dy = fs[i]
    if y >= dy:
        y -= dy
        x += 2 ** i
```


[[PAST2M]]
python 

```
for i in range(30 - 1, -1, -1):
    up = db_ups[i][cur % D]
    if countdown >= up:
        countdown -= up
        cur = db_next[i][cur % D]
        ret += 2 ** i
```


relevance
    - Doubling implementation of [[least common ancestor]] performs a dichotomous search on the doubling result.
    - When I verified with AOJ, it was a TLE unless I used this bisecting search method.

---
This page is auto-translated from [/nishio/ダブリング→二分探索](https://scrapbox.io/nishio/ダブリング→二分探索) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
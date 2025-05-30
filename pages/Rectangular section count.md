---
title: "Rectangular section count"
---

The problem of counting the number of points in the rectangular interval $0 \le x < T_x, 0 \le y < T_y$ when there are N points (x, y)
- $0 \le x, y < M$.

In particular, when computing $\sum_j[x_j < x_i$[[y_j < y_i]]] for each point [$ (x_i, y_i)
- If written in a simple loop, it is O(N^2), so we need to be creative when N is large.


    - [[Make one of the two dimensions a time axis.]]
    - Sort by x and use that as the time axis.
    - [[Fennic tree]]
    - Make y a domain of definition
- We just need to know how many of them satisfy y < y0 with x < x0 all added
    - If the domain is y and the value range is the number of occurrences, then sum
- If you have points with the same x, you need to group them by x in advance and add them after you are done summing
python

```
# grouping
from collections import defaultdict
P2 = defaultdict(list)
for i in range(M):
    x, y = PS[i]
    P2[y - 1].append(x - 1)

bit_init(H + 1)
for y in range(0, y0):
    ret += bit_sum(x0)
    for x in P2[y]:
        bit_add(x, 1)
```



- [[ABC186F]]
    - I used bit_set instead of bit_add because I wanted to know the number of blocked columns, not the number of columns in the range.
    - [[two dimensional cumulative sum]]
    - [https://algo-logic.info/submatrix-sum-queries/](https://algo-logic.info/submatrix-sum-queries/)
- [[Rectangular query]]

---
This page is auto-translated from [/nishio/長方形区間カウント](https://scrapbox.io/nishio/長方形区間カウント) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
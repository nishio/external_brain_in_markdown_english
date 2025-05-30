---
title: "Cosine similarity of 0.2 is extremely rare in higher dimensions"
---

In high dimensions of about 400 dimensions, [[Cosine similarity]] 0.2 is extremely rare, 1 in 10,000 times.
- I really wanted to try it in 768 dimensions, but after a million tries I got zero.
:
| dim | over 0.20 | over 0.22 | over 0.24 |
| -- | -- | -- | -- |
| 2 | 4297 | 4245 | 4177 |
| 10 | 2760 | 2554 | 2379 |
| 100  | 228 | 140 | 76 |
| 200 | 25 | 9 | 1 |
| 300 | 5 | 4 | 1 |
| 400 | 1 | 0 | 0 |

py

```
import numpy as np
for dim in [2, 10, 100, 200, 300, 400]:
    over020 = 0
    over022 = 0
    over024 = 0
    for i in range(10000):
        x = np.random.randn(dim)
        x = x / np.linalg.norm(x)
        if x[0] > 0.2:
            over020 += 1
        if x[0] > 0.22:
            over022 += 1
        if x[0] > 0.24:
            over024 += 1

    print(dim, over020, over022, over024)
```


[[higher dimensional space]].

---
This page is auto-translated from [/nishio/高次元においてコサイン類似度0.2は激レア](https://scrapbox.io/nishio/高次元においてコサイン類似度0.2は激レア) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
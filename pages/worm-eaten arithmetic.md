---
title: "worm-eaten arithmetic"
---

![image](https://gyazo.com/a66714b13fa8bfe5902356415d155d77/thumb/1000)

[https://twitter.com/drken1215/status/1389090596116000769?s=21](https://twitter.com/drken1215/status/1389090596116000769?s=21)

The factorial of 10 is 4 million at the highest, so the entire search can be solved with plenty of time to spare.
python

```
from itertools import permutations
for xs in permutations(range(10), 10):
    a, b, c, d, e, f, g, h, i, j = xs
    if a == 0 or c == 0 or f == 0:
        continue
    if (
        a * 1000 + b * 100 + a * 10 + b +
        c * 100 + d * 10 + e ==
        f * 10000 + g * 1000 + h * 100 + i * 10 + j
    ):
        print(xs)
```

output

```
(9, 3, 8, 6, 4, 1, 0, 2, 5, 7)
```


- [[Programmatic search]]

---
This page is auto-translated from [/nishio/虫食い算](https://scrapbox.io/nishio/虫食い算) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "The sum of the reciprocals is approximately 1"
---

![image](https://gyazo.com/539ec621bf6fbc7695ed8ea3b378e2a5/thumb/1000)
- [Twitter](https://twitter.com/yugokitajima/status/1388709059776286726?s=21)
Sum of reciprocals of values less than 10 with an error of less than 1
 Sum of reciprocals of values less than 10 with an error of less than 1

```
(2, 4, 7, 9) 1.0040
(2, 5, 6, 7) 1.0095
(2, 5, 6, 8) 0.9917
(3, 4, 6, 7, 9) 1.0040
(4, 5, 6, 7, 8, 9) 0.9956
```


python

```
from itertools import combinations
for n in range(4, 10):
    for xs in combinations(range(2, 10), n):
        s = sum(1 / x for x in xs)
        if abs(s - 1) < 0.01:
            print(xs, "%.4f" % s)
```


If we broaden the scope, we get examples like 2,3,7,42
- $1/2 + 1/3 + 1/7 + 1/42 = 21/42 + 14/42 + 6/42 + 1/42 = 42/42$
Even if you use the favorable number module to exclude the ones that are exactly 1, you still get the obvious ones like 2,3,7,43, which are not interesting.

- [[Programmatic search]]

---
This page is auto-translated from [/nishio/逆数の和が約1](https://scrapbox.io/nishio/逆数の和が約1) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
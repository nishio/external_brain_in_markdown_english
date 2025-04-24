---
title: "Range of influence of propagation downwards"
---

from  [[Propagation down the dual segment tree]]
Range of influence of propagation downwards
python

```
>>> table = [0] * SEGTREE_SIZE
>>> down_propagate(table, up(5), lambda x,y: "+", "*")
>>> debugprint(table)
|               *               |
|       *       |       +       |
|   +   |   *   |   0   |   0   |
| 0 | 0 | * | + | 0 | 0 | 0 | 0 |
|0|0|0|0|+|+|0|0|0|0|0|0|0|0|0|0|
```


---
This page is auto-translated from [/nishio/下への伝搬の影響範囲](https://scrapbox.io/nishio/下への伝搬の影響範囲) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
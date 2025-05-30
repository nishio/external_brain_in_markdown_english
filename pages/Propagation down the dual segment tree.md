---
title: "Propagation down the dual segment tree"
---

- In [[DSL 2 D Range Update Query]] I wrote
    - How should the "overwrite value" range action be defined?
    - The range action doesn't know which is later, whether the node is above or below.
    - So I made the value timestamped, and propagation downwards is a binary operation that "takes the one with the newer timestamp".
- This again implies the following
    - The implementation unintentionally assumed that the action was commutative.
    - Incorrect operation in case of non commutative "overwrite action
    - Converted to a commutative max operation by adding a timestamp.
- the problem is that you are not doing the propagation down correctly before the range action.
    - Half-delayed segment tree] omits the value segment tree when only a point acquisition is needed.
    - Furthermore, when the composition of actions is commutative, skipping propagation down [[dual segment tree]].
    - I correctly constructed a dual segment tree, but overlooked the "action composition is commutative".


Demo with two range actions and f and g overlapping out of order.
- If the propagation downwards is commutative, it doesn't matter if the order is switched here.
python

```
>>> range_update(table, 3, 10, lambda x: "f")
>>> range_update(table, 5, 15, lambda x: "g")
>>> debugprint(table)
|               0               |
|       0       |       0       |
|   0   |   f   |   g   |   0   |
| 0 | 0 | 0 | g | f | 0 | g | 0 |
|0|0|0|f|0|g|0|0|0|0|0|0|0|0|g|0|
```


The right way to do it when it is not commutative
- Propagate down before the second range action.
- It is guaranteed that the cell above the cell to be rewritten in the next range action is down.
- The range operator `lambda x: "g"` is the lower propagation binary operation `lambda x, y: x if x else y` with "g" in x.
python 

```
>>> table = [0] * SEGTREE_SIZE
>>> range_update(table, 3, 10, lambda x: "f")
>>> down_propagate(table, up(5), lambda x, y: x if x else y, 0)
>>> down_propagate(table, up(15), lambda x, y: x if x else y, 0)
>>> debugprint(table)
|               0               |
|       0       |       0       |
|   0   |   0   |   0   |   0   |
| 0 | 0 | 0 | f | f | 0 | 0 | 0 |
|0|0|0|f|f|f|0|0|0|0|0|0|0|0|0|0|

>>> range_update(table, 5, 15, lambda x: "g")
>>> debugprint(table)
|               0               |
|       0       |       0       |
|   0   |   0   |   g   |   0   |
| 0 | 0 | 0 | g | f | 0 | g | 0 |
|0|0|0|f|f|g|0|0|0|0|0|0|0|0|g|0|
```


Appendix: [[Range of influence of propagation downwards]].

- [[dual segment tree]]
- [[Segment tree visualization]]
---
This page is auto-translated from [/nishio/双対セグメント木の下への伝搬](https://scrapbox.io/nishio/双対セグメント木の下への伝搬) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
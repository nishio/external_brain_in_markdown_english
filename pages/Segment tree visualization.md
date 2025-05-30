---
title: "Segment tree visualization"
---

- I would like to organize the concept of [[segment tree]] through [[dual segment tree]] and [[delayed propagation segment tree]], not just simple segment trees.
- Taking advantage of being in Python, binary operations and actions are passed as arguments without hard-coding
- I don't care about speed because understanding is the goal.
- 1-origin, size 2-veki
- [Segment Tree study (2) | maspy's homepage](https://maspypy.com/segment-tree-%E3%81%AE%E3%81%8A%E5%8B%89%E5%BC%B72).
- [Source code here:](https://github.com/nishio/atcoder/blob/master/memo/segment_tree/segment_tree_vis.py)
    - When there is a discrepancy between the explanation here and the source doc, the source is correct, because I'm regression testing with doctest.

In the following, we have implemented segment trees, dual segment trees, delayed propagation segment trees, and even verified them with AOJ test cases, but we are still unable to identify whether the delayed propagation segment trees are TLE due to the flexible design or if there is something algorithmically wrong with them.

IDs are in this order.
python

```
>>> debugprint(range(SEGTREE_SIZE))
|                       1                       |
|           2           |           3           |
|     4     |     5     |     6     |     7     |
|  8  |  9  |  10 |  11 |  12 |  13 |  14 |  15 |
|16|17|18|19|20|21|22|23|24|25|26|27|28|29|30|31| 
```


Given an array, it can be constructed in O(N) while applying a binary operation to its neighbors.
- We're looking for a sum here, and this constructed tree can be used to get a fast range sum.
python

```
>>> table = [None] * SEGTREE_SIZE
>>> set_items(table, range(16))
>>> full_up(table, lambda x, y: f"{x}+{y}")
>>> debugprint(table, 3)
|             0+1+2+3+4+5+6+7+8+9+10+11+12+13+14+15             |
|        0+1+2+3+4+5+6+7        |     8+9+10+11+12+13+14+15     |
|    0+1+2+3    |    4+5+6+7    |   8+9+10+11   |  12+13+14+15  |
|  0+1  |  2+3  |  4+5  |  6+7  |  8+9  | 10+11 | 12+13 | 14+15 |
| 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10| 11| 12| 13| 14| 15|
```


Point Update
- Multiply the terminal value by a function (sometimes called an action)
    - Propagation of the action to the parent can be done by logN.
    - For example, +5 at the end of the segment tree will also cause the parent to be +5, so the entire segment tree can now be updated correctly.
python

```
>>> point_update(table, 3, lambda x: f"f({x})")
>>> debugprint(table, 4)
|                    f(0+1+2+3+4+5+6+7+8+9+10+11+12+13+14+15)                   |
|           f(0+1+2+3+4+5+6+7)          |         8+9+10+11+12+13+14+15         |
|     f(0+1+2+3)    |      4+5+6+7      |     8+9+10+11     |    12+13+14+15    |
|   0+1   |  f(2+3) |   4+5   |   6+7   |   8+9   |  10+11  |  12+13  |  14+15  |
| 0  | 1  | 2  |f(3)| 4  | 5  | 6  | 7  | 8  | 9  | 10 | 11 | 12 | 13 | 14 | 15 |
```


Another Pattern
- The terminal value is set independently of the previous value
    - In this case, the parent should propagate up while doing the binary operations of the two children
- Here are some cases where change cannot be expressed by action
    - For example, when an operation that takes max decreases the value
    - When the value is only increasing, it can be done by the action "take the new value and max
    - When the value is decreasing, even if x becomes 0 after finding max(x, y), the value of y is lost and cannot be returned.
python

```
>>> point_set(table, 3, "x", lambda x, y: f"{x}+{y}")
>>> debugprint(table, 3)
|             0+1+2+x+4+5+6+7+8+9+10+11+12+13+14+15             |
|        0+1+2+x+4+5+6+7        |     8+9+10+11+12+13+14+15     |
|    0+1+2+x    |    4+5+6+7    |   8+9+10+11   |  12+13+14+15  |
|  0+1  |  2+x  |  4+5  |  6+7  |  8+9  | 10+11 | 12+13 | 14+15 |
| 0 | 1 | 2 | x | 4 | 5 | 6 | 7 | 8 | 9 | 10| 11| 12| 13| 14| 15|
```


Demonstration of propagating max binomial operations up
python

```
# Point update, range max

>>> table = [0] * SEGTREE_SIZE
>>> set_items(table, range(16))
>>> full_up(table, max)
>>> debugprint(table)
|                       15                      |
|           7           |           15          |
|     3     |     7     |     11    |     15    |
|  1  |  3  |  5  |  7  |  9  |  11 |  13 |  15 |
|0 |1 |2 |3 |4 |5 |6 |7 |8 |9 |10|11|12|13|14|15|

>>> set_item(table, 5, 99)
>>> debugprint(table)
|                       15                      |
|           7           |           15          |
|     3     |     7     |     11    |     15    |
|  1  |  3  |  5  |  7  |  9  |  11 |  13 |  15 |
|0 |1 |2 |3 |4 |99|6 |7 |8 |9 |10|11|12|13|14|15|

>>> up_propagate_from_leaf(table, 5, max)
>>> debugprint(table)
|                       99                      |
|           99          |           15          |
|     3     |     99    |     11    |     15    |
|  1  |  3  |  99 |  7  |  9  |  11 |  13 |  15 |
|0 |1 |2 |3 |4 |99|6 |7 |8 |9 |10|11|12|13|14|15|
```



range contraction
- Binary operations can be used to reduce the range.
    - In Python, reduce
    - In Haskell, it's the fold system, in Ruby, it's inject, and so on.
    - In the segment tree context, I often see expressions that specify specific binary operations like Range sum or Range max.
    - I couldn't find a term that refers to "repeatedly applying a binary operation to multiple values within a range to obtain a single value," so I'll call it range contraction here.
        - It doesn't seem to be a major way to say it.
        - Some call it "convolution" (polysemous...)
- Binary operations must satisfy [associative law
    - Addition, multiplication, and max are OK
    - [[commutative law]] need not be satisfied
    - ...you can implement it like that, but with integer addition, multiplication, and max, the exchange rule is valid, so maybe some people haven't implemented it in a way that it doesn't have to be valid.
    - Cases that do not satisfy the law of exchange
        - If the value is a matrix and the binomial operation is a matrix product
        - [ARC008_D](https://atcoder.jp/contests/arc008/tasks/arc008_4)
            - Cannot be exchanged because the binary operation is $T \times S→T$, not $T\times T→T$.
python

```
>>> set_items(table, range(16))
>>> full_up(table, lambda x, y: f"{x}+{y}")
>>> range_reduce(table, 3, 11, lambda x, y: f"{x}+{y}", unity="0")
'0+3+4+5+6+7+8+9+10+0'

# Bin-op must be associative
>>> range_reduce(table, 3, 11, lambda x, y: f"({x}+{y})", unity="0")
'(((0+3)+4+5+6+7)+(8+9+(10+0)))'
```


Point update and range summation can be combined with point update and range contraction.
python

```
>>> table = [0] * SEGTREE_SIZE
>>> set_items(table, range(16))
>>> full_up(table, lambda x, y: f"{x}+{y}")
>>> debugprint(table)
|     0+1+2+3+4+5+6+7+8+9+10+11+12+13+14+15     |
|    0+1+2+3+4+5+6+7    | 8+9+10+11+12+13+14+15 |
|  0+1+2+3  |  4+5+6+7  | 8+9+10+11 |12+13+14+15|
| 0+1 | 2+3 | 4+5 | 6+7 | 8+9 |10+11|12+13|14+15|
|0 |1 |2 |3 |4 |5 |6 |7 |8 |9 |10|11|12|13|14|15|

>>> point_update(table, 5, lambda x: f"{x}+99")
>>> debugprint(table)
|                    0+1+2+3+4+5+6+7+8+9+10+11+12+13+14+15+99                   |
|           0+1+2+3+4+5+6+7+99          |         8+9+10+11+12+13+14+15         |
|      0+1+2+3      |     4+5+6+7+99    |     8+9+10+11     |    12+13+14+15    |
|   0+1   |   2+3   |  4+5+99 |   6+7   |   8+9   |  10+11  |  12+13  |  14+15  |
| 0  | 1  | 2  | 3  | 4  |5+99| 6  | 7  | 8  | 9  | 10 | 11 | 12 | 13 | 14 | 15 |

>>> range_reduce(table, 3, 11, lambda x, y: f"{x}+{y}", "0")
'0+3+4+5+6+7+99+8+9+10+0'
```


- [[dual segment tree]]
- Can be used for range update and point acquisition.

range update
- Multiply the action by the range between left and right
    - It is of logN order by not applying it to the terminal element.
python

```
>>> table = [""] * SEGTREE_SIZE
>>> set_items(table, range(16))
>>> range_update(table, 1, 11, lambda x: f"f")
>>> debugprint(table)
|                                               |
|                       |                       |
|           |     f     |           |           |
|     |  f  |     |     |  f  |     |     |     |
|0 |f |2 |3 |4 |5 |6 |7 |8 |9 |f |11|12|13|14|15|

>>> range_update(table, 3, 15, lambda x: f"{x}g")
>>> debugprint(table)
|                                                               |
|                               |                               |
|               |       fg      |       g       |               |
|       |   f   |       |       |   f   |       |   g   |       |
| 0 | f | 2 | 3g| 4 | 5 | 6 | 7 | 8 | 9 | f | 11| 12| 13|14g| 15|
```

- Use this to apply the action of (+1) and (+2) to a range in a range update
python

```
>>> table = [0] * SEGTREE_SIZE
>>> range_update(table, 1, 11, lambda x: x + 1)
>>> debugprint(table, maxsize=4)
|               0               |
|       0       |       0       |
|   0   |   1   |   0   |   0   |
| 0 | 1 | 0 | 0 | 1 | 0 | 0 | 0 |
|0|1|0|0|0|0|0|0|0|0|1|0|0|0|0|0|

>>> range_update(table, 3, 15, lambda x: x + 2)
>>> debugprint(table, maxsize=4)
|               0               |
|       0       |       0       |
|   0   |   3   |   2   |   0   |
| 0 | 1 | 0 | 0 | 1 | 0 | 2 | 0 |
|0|1|0|2|0|0|0|0|0|0|1|0|0|0|2|0|
```

- If we want the fifth value, we can propagate the action downward from the parent to it.
python

```
>>> down_propagate_to_leaf(table, 5, add, 0)
>>> debugprint(table, maxsize=4)
|               0               |
|       0       |       0       |
|   0   |   0   |   2   |   0   |
| 0 | 1 | 0 | 3 | 1 | 0 | 2 | 0 |
|0|1|0|2|3|3|0|0|0|0|1|0|0|0|2|0|

>>> down_propagate_to_leaf(table, 9, add, 0)
>>> debugprint(table, maxsize=4)
|               0               |
|       0       |       0       |
|   0   |   0   |   0   |   0   |
| 0 | 1 | 0 | 3 | 0 | 2 | 2 | 0 |
|0|1|0|2|3|3|0|0|3|3|1|0|0|0|2|0|
```

    - [[Propagation down the dual segment tree]]
    - If the action is not commutative, there must be downward propagation before range action.

- Continue [[Visualization of delay propagation segment trees]].

Verified
- [DSL_2_A Range Minimum Query (RMQ)](https://onlinejudge.u-aizu.ac.jp/courses/library/3/DSL/2/DSL_2_A)
python

```
def main():
    N, Q = map(int, input().split())
    depth = N.bit_length() + 1
    set_depth(depth)
    table = [INF] * SEGTREE_SIZE

    for _q in range(Q):
        q, x, y = map(int, input().split())
        if q == 0:
            # update
            point_set(table, x, y, min)
        else:
            # find
            print(range_reduce(table, x, y + 1, min, INF))
```

- [DSL_2_B Range Sum Query](https://onlinejudge.u-aizu.ac.jp/courses/library/3/DSL/2/DSL_2_B)
python

```
def main():
    from operator import add
    N, Q = map(int, input().split())
    depth = N.bit_length() + 1
    set_depth(depth)
    table = [0] * SEGTREE_SIZE

    for _q in range(Q):
        q, x, y = map(int, input().split())
        if q == 0:
            # add
            point_update(table, x, lambda x: x + y)
        else:
            # sum
            print(range_reduce(table, x, y + 1, add, 0))
```

- [[DSL_2_D Range Update Query]]
- [DSL_2_E Range Add Query](https://onlinejudge.u-aizu.ac.jp/courses/library/3/DSL/2/DSL_2_E)
python

```
def main():
    from operator import add
    N, Q = map(int, input().split())
    depth = N.bit_length() + 1
    set_depth(depth)
    table = [0] * SEGTREE_SIZE

    for time in range(Q):
        q, *args = map(int, input().split())
        if q == 0:
            # update
            s, t, value = args
            range_update(table, s, t + 1, lambda x: x + value)

        else:
            # find
            print(down_propagate_to_leaf(
                table, args[0], add, 0))
```


---
This page is auto-translated from [/nishio/セグメント木の可視化](https://scrapbox.io/nishio/セグメント木の可視化) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
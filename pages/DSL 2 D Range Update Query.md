---
title: "DSL 2 D Range Update Query"
---

from  [[Segment tree visualization]]
DSL_2_D Range Update Query
- [DSL_2_D Range Update Query](https://onlinejudge.u-aizu.ac.jp/courses/library/3/DSL/2/DSL_2_D)
    - How should the "overwrite value" range action be defined?
    - The range action doesn't know which is later, whether the node is above or below.
    - So I made the value timestamped, and propagation downwards is a binary operation that "takes the one with the newer timestamp".
    - Alternative solution [[Propagation down the dual segment tree]].
python

```
def main():
    N, Q = map(int, input().split())
    depth = N.bit_length() + 1
    set_depth(depth)
    action_unity = (-1, INF)
    table = [action_unity] * SEGTREE_SIZE

    for time in range(Q):
        q, *args = map(int, input().split())
        if q == 0:
            # update
            s, t, new_value = args
            range_update(table, s, t + 1, lambda x: (time, new_value))

        else:
            # find
            print(down_propagate_to_leaf(
                table, args[0], max, action_unity)[1])
```


---
This page is auto-translated from [/nishio/DSL 2 D Range Update Query](https://scrapbox.io/nishio/DSL 2 D Range Update Query) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
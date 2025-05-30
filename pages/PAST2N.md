---
title: "PAST2N"
---

![image](https://gyazo.com/e061127462d65fbc91305c7902b100a7/thumb/1000)
[N - Building Construction](https://atcoder.jp/contests/past202004-open/tasks/past202004_n)

from  [[Second Algorithm Practical Skills Test]]
PAST2N
- Thoughts.
    - Find 5,000 squares that contain it for a point and add up the cost.
    - However, linear orders will not make it in time.
    - what to do about it
    - If it were one-dimensional, we would record the points of variation of the cumulative sum and perform a binary search, but this time it is two-dimensional.
    - Is it the 2-D Imosu method?
        - It seems impossible to do it in two dimensions since the coordinates are 10^5 even after compressing the coordinates.
- Official Explanation
        - [[planar scanning]]
- A new thought.
        - [[Rectangular section add]]
    - Maybe this needs a [[Query look-ahead]].
    - If you process N squares per query, no matter how fast the individual process is, you'll never make it in time.
    - Include the boundaries of the intervals, so they are mixed and sorted by (y, x)
    - ![image](https://gyazo.com/2fd0b0bd0c92f206061c4b4ef25c4fec/thumb/1000)
- mounting
    - I noticed it when I tried to make a segmented tree.
        - Value range 10^9 → [[coordinate compression]] required
        - [[RangeAdd is two PointAdd]]
    - When RangeAdd and Read overlap at the same coordinates, the starting RangeAdd must be processed before Read because of the "square corners are also inside the square" specification.
        - Conversely, the closing RangeAdd must be processed later.
        - Let's shift the coordinates by 0.5.
    - Sample 1 came through, but negative values came up in sample 2.
        - →The mistake was accessing the segment tree with the original coordinates, even though the coordinates were compressed.
- AC
python

```
def solve(N, Q, SS, QS):
    xs = []
    for x, _, width, _ in SS:
        xs.append(x)
        xs.append(x + width)
    for x, _ in QS:
        xs.append(x)
    xs.sort()
    x2i = {}
    for i, x in enumerate(xs):
        x2i[x] = i
    i2x = xs

    commands = []
    for x, y, width, cost in SS:
        start = x2i[x]
        end = x2i[x + width]
        commands.append((
            y, start - 0.5,
            "add",
            start, end, cost
        ))
        commands.append((
            y + width, end + 0.5,
            "add",
            start, end, -cost
        ))
    for x, y in QS:
        commands.append((
            y, x2i[x],
            "read",
            None, None, None
        ))
    commands.sort()
    result = {}

    # segtree
    from operator import add
    set_width(len(x2i) + 10)
    table = [0] * SEGTREE_SIZE
    for y, x, typ, start, end, cost in commands:
        if typ == "add":
            # range add as two point_add
            point_set(table, start, get_value(table, start) + cost, add)
            point_set(table, end + 1, get_value(table, end + 1) - cost, add)
        else:
            # point read as range sum
            v = range_reduce(table, 0, x + 1, add, 0)
            result[(i2x[x], y)] = v

    # print answer
    for q in QS:
        print(result[q])
```



---
This page is auto-translated from [/nishio/PAST2N](https://scrapbox.io/nishio/PAST2N) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
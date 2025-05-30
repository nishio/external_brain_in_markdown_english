---
title: "PAST5E"
---

[E - stamp](https://atcoder.jp/contests/past202012-open/tasks/past202012_e)
![image](https://gyazo.com/96531e5dba571b147d99cf54cec7253f/thumb/1000)
- Just do a simple search for all of them.
- To search the whole area without overflowing, [[sentry]] is added to the non-stamped side to cover the width of the stamp.
- The code itself to attach the guard was already written.
        - [[Putting a guard on when loading a map]]
    - I've never read two at once before, so I was writing a guarded width in global space.
    - This time I read two, so the code recalculates without reference to that value.
        - There is room for improvement, but it seems to be used infrequently...
- I didn't expect rotation, so I wrote a new one this time.
    - Length and width are exchanged during rotation
    - Only the side of the stamp should be replaced, but it was taken wrong and WA'd.
python

```
def solve(H, W, world, stamp):
    S = max(H, W)
    # world
    WW = W + 2 * S
    WH = H + 2 * S
    # stamp
    SW = W
    SH = H

    def conflict():
        for x in range(SW):
            for y in range(SH):
                if stamp[y * SW + x] == 0:
                    if world[(sy + y) * WW + (sx + x)] == 0:
                        # conflict
                        return True

    for _rot in range(4):
        for sx in range(S + W):
            for sy in range(S + H):
                if conflict():
                    continue
                return True
        # rotate
        new_stamp = [0] * (W * H)
        for x in range(SH):
            for y in range(SW):
                new_stamp[y * SH + x] = stamp[(SH - 1 - x) * SW + y]
        stamp = new_stamp
        SW, SH = SH, SW

    return False
```

- Official Explanation
    - If you have the side of the stamp as a sequence of coordinates, you can write the implementation of rotation in a straightforward manner, I see.
        - [[Make a two-dimensional array into a sequence of coordinates]]

---
This page is auto-translated from [/nishio/PAST5E](https://scrapbox.io/nishio/PAST5E) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
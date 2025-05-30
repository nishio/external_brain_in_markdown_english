---
title: "PAST4G"
---

from  [[Fourth Algorithm Practical Skills Test]]
PAST4G
[G - Village Maintenance](https://atcoder.jp/contests/past202010-open/tasks/past202010_g)
- Thoughts.
    - 100 squares at most
    - If there is one connected component, all walls
    - If two, a wall connecting them.
    - If more than three, a wall connecting them.
    - Or four of them.
    - 0 if 5 or more
    - Library Improvement Memo
        - It would be nice to be able to specify how to encode what I read.
        - In the library I had prepared, the walls are 0 and the roads are 1, but in this case I wanted to paint by color number, so I used a larger number.
        - Keep 4 directions, 8 directions, etc. as constants.
            - I used it for the C problem as well.
    - supplement
        - Paint from corner to corner with DFS.
        - Increment the color count if squares not yet painted are found
        - 0 if the number of colors is 5 or more.
        - For each square, check the colors on all four sides and count the number of squares in which all colors appear.
python

```
def solve(H, W, data):
    DOT = 100
    BLOCK = 101

    def paint(pos, color):
        data[pos] = color
        for d in [-WIDTH, -1, +1, +WIDTH]:
            if data[pos + d] == DOT:
                paint(pos + d, color)

    color = 0
    for pos in allPosition():
        if data[pos] == DOT:
            paint(pos, color)
            color += 1

    if color >= 5:
        return 0
    ret = 0
    for pos in allPosition():
        if data[pos] != BLOCK:
            continue
        color_exists = [0] * 4
        for d in [-WIDTH, -1, +1, +WIDTH]:
            c = data[pos + d]
            if c < 4:
                color_exists[c] = 1
        if sum(color_exists) == color:
            ret += 1

    return ret
```

- Official Explanation
    - The map is quite small, 10 x 10.
    - So, using each wall as a starting point, "If I break that wall, will all non-wall squares be reachable?" is still 10^4 to spare.
        - O(N^4)
    - My solution was O(N^2), so it was overkill.

---
This page is auto-translated from [/nishio/PAST4G](https://scrapbox.io/nishio/PAST4G) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "ABC186F"
---

from [[ABC186]]
ABC186F
- ![image](https://gyazo.com/ecac49bfec2162e0a6e196eff9d3cd89/thumb/1000)
- [F - Rook on Grid](https://atcoder.jp/contests/abc186/tasks/abc186_f)
- unfinished
- Thoughts.
    - There are two ways to get there: vertically and horizontally.
    - If you count and add them individually, you get a double count where you can get there in two different ways.
    - Consider efficient counting of double-counted objects.
        - Wouldn't it be easier to [[have an after-event]]?
        - In other words, "count the squares you can't reach and subtract from the whole.
        - ![image](https://gyazo.com/0bfc6272ea8fb38766722b788bda44bb/thumb/1000)
        - This intersection is the "mass you can't reach."
    - Let `minY[x]` be the smallest y at each x
        - What I want is the number of `minX[y] <= x` in the range `minY[[x]] < y
    - I've seen these patterns before...
        - Search for related items from Scrapbox
                - [[Deletable set with inequality condition]]
            - [[ACL1A]]
        - The following elements could be used, although they are not entirely consistent with the purpose of this project
                - Use [Fennic tree
            - The value range is 0/1, representing the absence or presence of a value
    - Summary [[Rectangular section count]].
    - Write code that naively counts the number of `minX[y] <= x` in the range `minY[x] < y` and implement a version that uses a phenic tree to achieve the same result
    - Submission → WA
    - While examining the discrepancy between the naive implementation and the phoenic tree implementation in a random test, I realized that the naive implementation was wrong.
        - this kind of pattern
        - ![image](https://gyazo.com/3fc29bf88b7be3fcc5ccbe6a7b25690e/thumb/1000)
- Official Explanation
    - Policy of using phenic trees is OK.
    - I'm not counting the places I can't get to, I'm counting the places I can get to in two different ways.
    - AC
python

```
def solve(H, W, M, PS):
    minX = [H] * W
    minY = [W] * H
    for x, y in PS:
        minX[y - 1] = min(minX[y - 1], x - 1)
        minY[x - 1] = min(minY[x - 1], y - 1)

    ret = 0
    # horizontal -> vertical
    for x in range(0, minX[0]):
        ret += minY[x]

    # grouping
    from collections import defaultdict
    P2 = defaultdict(list)
    for i in range(M):
        x, y = PS[i]
        P2[y - 1].append(x - 1)

    bit_init(H + 1)
    x0 = minX[0]
    for y in range(0, minY[0]):
        x1 = minX[y]
        if x1 > x0:
            ret += x1 - x0
            x1 = x0
        ret += bit_sum(x1)
        for x in P2[y]:
            bit_set(x, 1)

    return ret
```



---
This page is auto-translated from [/nishio/ABC186F](https://scrapbox.io/nishio/ABC186F) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
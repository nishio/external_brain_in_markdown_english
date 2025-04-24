---
title: "Rectangular section add"
---

I want to add to a rectangular section of two-dimensional space and read it out in points.
- Alternative representation: given a set of rectangles and a point. We want the sum of the number/cost of rectangles containing points [[PAST2N]].

- [[Make one of the two dimensions a time axis.]]
- sort add and read on one axis and time axis on the other
    - Range Add at one point and negative Range Add at another point.
    - ![image](https://gyazo.com/2fd0b0bd0c92f206061c4b4ef25c4fec/thumb/1000)
- When RangeAdd and Read overlap at the same coordinates
    - If the specification is "inside corners too":.
        - The start RangeAdd must be processed before Read.
        - End RangeAdd must be processed after Read
    - Shift the coordinates by 0.5
        - Start RangeAdd: x -= 0.5
        - End RangeAdd: x += 0.5
- When the range of x values is large, [[coordinate compression]] is required
    - [RangeAdd is two PointAdd

- [[Rectangular query]]

---
This page is auto-translated from [/nishio/長方形区間add](https://scrapbox.io/nishio/長方形区間add) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
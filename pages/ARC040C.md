---
title: "ARC040C"
---

[C - Z painted](https://atcoder.jp/contests/arc040/tasks/arc040_c)
- ![image](https://gyazo.com/766026735d7179c0d4a11f824e20f5e9/thumb/1000)
- Thoughts.
    - The floor can be interpreted as expanding into a one-dimensional array and painting an area of length N+1
            - Pattern with no guard on [Putting a guard on when loading a map
    - I wonder if the minimum number of times is good because they are applied in order from the end, sounds good, but I want to prove it.
    - If a section is painted starting from the smallest square that has not yet been painted, there are equal or fewer squares remaining than if the section is painted from more to the left.
    - If you paint more from the right, you will have leftover paint, so you have to paint again from the left to paint it.
    - OK
    - To recap.
        - When painting a minimum number of moves, there exists one move that is painted from the left-most square. It is shown that there exists a minimum number of moves painting such that this is the one starting from the left-most not yet painted square.
        - When the starting point is more to the left, the "unpainted squares" after that paint is done are non-decreasing, so there is no possibility of a less labor intensive paint job
        - When the starting point is more to the right, the square of interest is left unpainted, so it is necessary to paint over it separately. This is inconsistent with being a "move that paints from more left".
        - Therefore, it is shown that the first move is made by painting starting from the leftmost square that has not been painted.
- Official Explanation
    - OK

[[ARC040]]
[[ARC]]

---
This page is auto-translated from [/nishio/ARC040C](https://scrapbox.io/nishio/ARC040C) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
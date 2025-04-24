---
title: "ABC124D"
---

[D - Handstand](https://atcoder.jp/contests/abc124/tasks/abc124_d)
- ![image](https://gyazo.com/5a49fbb79162d86370011f5556a57803/thumb/1000)
- Thoughts.
    - When the areas to be inverted overlap, it is acceptable to assume that the sections do not overlap because there are non-overlapping inversion methods that produce the same result [[It is acceptable to assume that the sections do not intersect.]]
            - [[Composition of interval inversion is XOR]]
    - Therefore, we can turn over the K chunks of 0's to make the longest chunk of 1's
    - To eliminate conditional branching, which considers a block of 1's of length 0 or greater at the beginning and end.
    - Just find the point where the distance between the starting point of the i-th lump of 1 and the end point of the i+k-th lump of 1 is the greatest
    - Enumerate start and end points in linear time and find the maximum in linear time
- Official Explanation OK

---
This page is auto-translated from [/nishio/ABC124D](https://scrapbox.io/nishio/ABC124D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
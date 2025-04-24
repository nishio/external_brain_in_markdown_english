---
title: "ABC174F"
---

[F - Range Set Query](https://atcoder.jp/contests/abc174/tasks/abc174_f)
![image](https://gyazo.com/d1e4ee6d9ee7b595405a406cf1c6fbe7/thumb/1000)

- Thoughts.
    - If it can be determined in logarithmic order whether or not color ci exists within the range, it can be done in time.
    - dichotomous search
- mounting
    - 7 minutes to implement, submit, TLE
    - Oh, not at all, even if we can determine if each color is in range in logarithmic order for every N cases, it's O(QNlogN).
- Consideration again
        - [[Query look-ahead]] and [Make one of the two dimensions a time axis.
        - Still the worst O(QN).
    - Make a set of ball colors every 2^n blocks.
        - The total number of sets is 2N-1
        - A set of colors for the requested interval can be created by merging logN times.
            - But if you do it normally, the merge is heavy and you end up with O(QN).
            - Use [[binary heap]] with light merging?
- Official Explanation
    - Interval queries are segment trees, but merging is heavy
        - [[Query look-ahead]] and [[Make one of the two dimensions a time axis.]]
        - Maintain the "rightmost sphere location" of each color at each point in time.
        - If this is greater than L, then the color is in the range, constant order
        - But this is still O(QN)
        - Put the "rightmost sphere location" of each color into the [Fennic tree
            - Counting the number of pieces is logarithmic order in the range sum
            - I see, so this is the point.
                - [[Large and small comparison with many things → Fennic tree]]

- 3TLE

- [[Lots of queries matter.]]
from [[ABC174]]
ARC174F
- [https://hama-du-competitive.hatenablog.com/entry/2016/10/01/001418](https://hama-du-competitive.hatenablog.com/entry/2016/10/01/001418)
- [https://twitter.com/maspy_stars/status/1290139299011129344?s=21](https://twitter.com/maspy_stars/status/1290139299011129344?s=21)
- [https://twitter.com/tktk_snsn/status/1290222202843889665?s=21](https://twitter.com/tktk_snsn/status/1290222202843889665?s=21)
- [[Mo's algorithm]]

---
This page is auto-translated from [/nishio/ABC174F](https://scrapbox.io/nishio/ABC174F) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
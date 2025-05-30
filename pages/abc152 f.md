---
title: "abc152 f"
---

from  [[Typical ideas for coming up with solutions in competitive programming]]
abc152_f
[https://atcoder.jp/contests/abc152/tasks/abc152_f](https://atcoder.jp/contests/abc152/tasks/abc152_f)
- N=50
- At least one black must be on the path connecting the two points of the tree.
        - [[Consider the after-event]]
    - All paths are white."
    - This is easy to find, if the length of the path is x, then about 2^(N-x)
    - You look at one constraint, and the number of cases where it's violated is easily obtained. There's more than one constraint, and the cases that are satisfied at the same time are double counted -> [[principle of inclusion]].
    - There are 20 constraints. 2^20 is a tight squeeze. do we DP?
    - Can the paths of multiple constraints overlap? Of course there can.
        - This is tricky, huh?
        - Need to get the "number of overlapping edges" fast when adding paths to a set of multiple paths?
            - Precompute [[least common ancestor]]?
- Official Explanation
    - OK up to the principle of inclusions and removals
    - It seems to be a "cumulative sum on a tree to find the [[least common ancestor]]" for multiple overlapping paths, but I don't understand it.
        - They're counting by O(N+M) in all patterns of 2^20.
- another solution
    - The sides are 50 high, so it fits int64.
    - If the paths are represented in bits, the superposition can be calculated by OR.

---
This page is auto-translated from [/nishio/abc152 f](https://scrapbox.io/nishio/abc152 f) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
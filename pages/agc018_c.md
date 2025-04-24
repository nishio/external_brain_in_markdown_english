---
title: "agc018_c"
---

[C - Coins](https://atcoder.jp/contests/agc018/tasks/agc018_c)
![image](https://gyazo.com/a699700f574f70d6d75e4d04dcf31e26/thumb/1000)
- Thoughts.
    - First, everything is set to A, then sort the "gain from changing to B" and "gain from changing to C" and take it from the largest to the smallest.
    - This is probably not good enough. Because there's a pattern of, "If we go with B, it's a loss, but if we go with C, it's a huge loss, so we have to go with B."
- Official Explanation
    - When there are two types, a greedy algorithm that sorts by difference and takes the larger one is valid, so I want to transform the problem and then return to
    - A never comes to the left of B when sorted by B-A, in which case [Replacement does not make it worse.
    - So if we draw a boundary, we can come down to two kinds of problems.
            - [[Full search for boundary location]]
    - [[doing]]

---
This page is auto-translated from [/nishio/agc018_c](https://scrapbox.io/nishio/agc018_c) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
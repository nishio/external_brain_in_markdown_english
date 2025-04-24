---
title: "ABC014C"
---

[C - AtColor](https://atcoder.jp/contests/abc014/tasks/abc014_3)
- ![image](https://gyazo.com/bcea3a19aa82653da975c281ab5f0e67/thumb/1000)
- Thoughts.
    - The answer can be obtained by sorting pairs of starting point and +1, and ending point and -1, and accumulating them from the beginning and taking the maximum value.
        - Even if they're covered by the same value, the -1 comes first, so no fraudulently large value is created.
    - 200,000 O(NlogN), so I think you'll be fine.
            - [[Estimating computational quantities]]
        - Hmmm, it still looks like you can afford it.
- Official Explanation
    - Officials use the 1000000 sequence, but yikes.
    - I wonder if my solution is equivalent to having [[coordinate compression]] and then [[Imosu Act (fifth highest of the eight hereditary titles, later demoted to sixth highest of eight)]].

- [[Small order from official]]
[[ABC014]]

---
This page is auto-translated from [/nishio/ABC014C](https://scrapbox.io/nishio/ABC014C) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
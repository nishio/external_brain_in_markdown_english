---
title: "ABC165C"
---

[C - Many Requirements](https://atcoder.jp/contests/abc165/tasks/abc165_c)
- ![image](https://gyazo.com/43ed1564d189529091d94cd9021c154e/thumb/1000)
- Thoughts.
    - Hmmm, I don't think I'll make it if I explore normally.
    - But it doesn't seem to be a DP to be fixed from the front since the scoring is not adjacent to each other.
        - Even if you can get a high score in the front, you can't get a score in the back if you choose to do that.
    - I wonder if the NM is 100 at the highest, so I'll just graph it and solve it with flow.
        - I wonder how you would describe the scoring thing when two vertices are selected.
- Official Explanation
    - Full search
    - C(20,10) is about 180,000
        - So multiply it by 50 or so and you're still good to go.
            - [[Estimating computational quantities]] Miss.

---
This page is auto-translated from [/nishio/ABC165C](https://scrapbox.io/nishio/ABC165C) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
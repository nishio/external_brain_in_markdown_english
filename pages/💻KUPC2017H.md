---
title: "💻KUPC2017H"
---

[H - Make a Potion](https://atcoder.jp/contests/kupc2017/tasks/kupc2017_h)
![image](https://gyazo.com/f2dc4a6aa7acee93e06792643d101b59/thumb/1000)
- Thoughts.
    - Known to be attributed to minimum cuts
    - No two options, but [[3 or more options with minimum cuts]] is acceptable
    - But the range of v is up to 10^6, so it's hard to make all of them vertices.
    - Do we need [[coordinate compression]] to select only the vertices relevant to the constraint?
        - If the potency is positive, it is more profitable to include up to a-1 just before the constraint.
        - If the potency is negative, it is beneficial to stop just short of the constraint b
- mounting
    - ![image](https://gyazo.com/9691ec6d4f71c67caf7c82d036afbba4/thumb/1000)
    - ![image](https://gyazo.com/8ca69974b4a52090025c6d4f0c93111b/thumb/1000)

    - The irregular number of vertices is a pain to implement...


---
This page is auto-translated from [/nishio/💻KUPC2017H](https://scrapbox.io/nishio/💻KUPC2017H) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
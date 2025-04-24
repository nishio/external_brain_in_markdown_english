---
title: "arc046_b"
---

[B - Operation Stone Removal](https://atcoder.jp/contests/arc046/tasks/arc046_b)
![image](https://gyazo.com/d9db142ea9bb9d964a6454189f0dacea/thumb/1000)
- Thoughts.
    - If there is less than A remaining and it is the first move's turn, the first move wins.
    - If there is less than B remaining and it is the late player's turn, the late player wins.
    - Suppose B is less than A (wlog)
    - The first player wins if A+1 or less in the second turn.
    - In the first move, when A+2, even if 1 is taken, it is still greater than B, so the first move wins.
        - If it's 2A+1 or less, you can take the first move to win.
        - If the side with the highest number of moves wins the game...
- Official Explanation
    - Your intuition is right, you just need to show it in a proper and comprehensive case study.

- [[competitive problem]]
- [[Asymmetric Games]]

---
This page is auto-translated from [/nishio/arc046_b](https://scrapbox.io/nishio/arc046_b) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
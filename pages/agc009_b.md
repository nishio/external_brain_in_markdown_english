---
title: "agc009_b"
---

[B - Tournament](https://atcoder.jp/contests/agc009/tasks/agc009_b)
![image](https://gyazo.com/663b6504cc72eb8faea49ef05870d0f2/thumb/1000)
- Thoughts.
    - What does the information given in the question mean?
    - So the LCA of i and ai is lower than the LCA of 1 and i.
    - The height must be as high as the number of people x who fought against 1 and lost, the same with respect to those who fought against x and lost, and so on down recurrently.
    - The length of the game is fixed when it comes to those who have not lost to anyone else.
    - Long rows should be branched as close to the root as possible, and finalized in order on the way back.
- Official Explanation OK
    - In the words of the official explanation, when the child is determined, the parent is determined DP, and how to arrange the child when it is determined is the greedy method.

---
This page is auto-translated from [/nishio/agc009_b](https://scrapbox.io/nishio/agc009_b) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
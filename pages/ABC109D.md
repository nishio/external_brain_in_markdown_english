---
title: "ABC109D"
---

[D - Make Them Even](https://atcoder.jp/contests/abc109/tasks/abc109_d)
- ![image](https://gyazo.com/1c2b233f267cb0812cd14d32d2d5bd4a/thumb/1000)
- Thoughts.
    - This paragraph is a misunderstanding
        - There is no benefit to moving something that is already even.
        - Losses when odd numbers join even numbers.
        - Does it make sense to move even numbers if it's to open the way for them not to merge?
    - I mistakenly thought it was moving the whole mountain, but it was "moving one piece."
        - then the largest solution is the one that once all the coins in the odd-numbered pile are removed and two coins are dealt in each of the zero squares
        - You're asked to output the steps, but they don't have to be the shortest steps, just process them in order.
- Official Explanation
    - I see in the sample that "an even number of coins were placed" includes zero coins.
    - Then we just move one from one odd-numbered pile to another odd-numbered pile.

---
This page is auto-translated from [/nishio/ABC109D](https://scrapbox.io/nishio/ABC109D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
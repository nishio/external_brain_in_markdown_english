---
title: "AGC006B"
---

[B - Median Pyramid Easy](https://atcoder.jp/contests/agc006/tasks/agc006_b)
- ![image](https://gyazo.com/f9fa97d6fe4f90d6b2757f42bbf6c3f3/thumb/1000)
- Thoughts.
    - When two steps, the top is 2.
    - the time for disasters (similar to 'the witching hour' but not midnight)
        - 3 in a normal arrangement.
        - For example, 5 1 2 4 3 would be two, so the top would be 2.
        - Similarly, we can do the same for 4.
    - the time of the four stages of life (birth, old age, disease, death)
        - 7 1 2 6 3 4 5 and the top is 2 2 3 4 4 which is 3
    - Hypothesis: Top only moves in the range of median plus or minus 1?
- Official Explanation
    - Hypothesis is incorrect.
    - If two squares have the same value, then the two squares above them have the same value, regardless of the other squares.
        - When thinking about specifics, it's not a good idea to think only about the bottom layer, where the different values are lined up.
        - [[Once you're in a certain state, you can't get out.]]
        - [[Median -> What if two values are the same?]]
- problem partitioning
        - [[median]]
        - [[Repeated results of the same operation]]

---
This page is auto-translated from [/nishio/AGC006B](https://scrapbox.io/nishio/AGC006B) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
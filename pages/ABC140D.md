---
title: "ABC140D"
---

[D - Face Produces Unhappiness](https://atcoder.jp/contests/abc140/tasks/abc140_d)
- ![image](https://gyazo.com/8e967088bef468ccfed5f2beb01a1dd3/thumb/1000)
- Thoughts.
    - The rotation only changes the score for up to four people before and after the end of the row.
    - The maximum score is when everyone is looking in the same direction.
    - Add an inward-facing guard at the end.
    - Rotation does not change the score when the outside of the area is facing a different direction.
    - Rotation does not change the score even when the inside of the area is oriented differently.
    - When you have both, your score increases by 2. This is the best move you can make.
    - Count how many areas can be obtained in linear order (there are two ways to align to the right or to the left, so take the larger one).
    - The smaller of that number and K multiplied by 2 is the score increment
- Official Explanation
    - approximately the same

[[ABC140]]

---
This page is auto-translated from [/nishio/ABC140D](https://scrapbox.io/nishio/ABC140D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "AdaBoost"
---

![image](https://gyazo.com/42349cc0f811f920dac8139fbc6b40b9/thumb/1000)

- with a "weak learner" that can only cut vertically or horizontally.
- Study "difficult problems" such as (1, 1) above right.
    - A difficult problem that cannot be expressed by a single horizontal and vertical cut in the first place.
- Let's say that in the first test you answered like (1, 2), cut vertically and to the right of it.
    - The red text in the upper left (1, 4) is in the wrong place.
- The next time you study, focus on the problem that you got wrong (2, 1).
- Suppose that in the second test, the answer is (2, 2).
    - Combining the two answers (2, 3), notice that the two in the center are not known to be A or B (2, 4).
- The third study will focus on these central two (3, 1).
- Suppose that on the third test, you cut horizontally and answered as (3, 2).
    - The student correctly learns to take a majority vote of three answers (3, 3) (3, 4) and the question (1, 1).

---
This page is auto-translated from [/nishio/AdaBoost](https://scrapbox.io/nishio/AdaBoost) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
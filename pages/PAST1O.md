---
title: "PAST1O"
---

[O - Endurance Games](https://atcoder.jp/contests/past201912-open/tasks/past201912_o)
![image](https://gyazo.com/a96588a2faae92214acd0e7b6e653209/thumb/1000)
- Thoughts.
    - Given the previous value x, the probability of "succeeding in rolling that dice" is obtained for each dice
        - The smaller the eye, the higher the probability of success, but the lower the success rate of the next dice.
    - Dice are 3 x 10^4, eyes are 1.8 x 10^5, all different
    - Since x can only take the second value, it is sorted and calculated from the largest value.
        - For largest x, expected value is 0
        - Can be calculated with DP
    - A naive DP would be to find the one that maximizes the expected value out of all the dice, which is costly and exceeds 10^9.
    - Since all the eyes are different, there is only one dice that changes the "eye and x's size relationship" when x is reduced by one step.
            - [[Notice what changes.]]
        - And monotonous increase
            - Compare the dice with the largest expected value and the updated dice, and take the one with the larger expected value, which can be done in constant order.
        - This will get you there in time.
- Official Explanation
    - The eyes can be sorted and reassigned to sequential numbers since only large and small eyes are used = [[coordinate compression]].

- [[Expected DP]]
- [[First Algorithm Practical Skills Test]]

---
This page is auto-translated from [/nishio/PAST1O](https://scrapbox.io/nishio/PAST1O) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "ABC181E"
---

[E - Transformable Teacher](https://atcoder.jp/contests/abc181/tasks/abc181_e)
![image](https://gyazo.com/7548e6371791424aba9f76028ec6bfa1/thumb/1000)

from [[ABC181]]
ABC181E
- Thoughts.
    - I want to minimize the sum of the differences between pairs of numbers, but only one number X can be changed in M ways
    - M is more than 10^5 so is it hard to try them all?
        - Good if the sum of the differences can be obtained in constant or logarithmic order
    - Consider the sum of the differences
    - If there is an overlap when the pair is considered as a range, we can exchange them and make the difference much smaller [[It is acceptable to assume that the sections do not intersect.]]
        - Then, the best solution is to greedily pair them from the smallest to the largest.
    - Make cumulative sums paired from the top and paired from the bottom, excluding those that change value.
                - Same idea as [Cumulative product from left to right
        - Binary search to find how many X's are in, logarithmic order
        - Put X in the odd-numbered ones, each of which is a cumulative sum of a constant order
- Official Explanation OK
    - There is an option to solve by the shaku-tori method.

---
This page is auto-translated from [/nishio/ABC181E](https://scrapbox.io/nishio/ABC181E) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
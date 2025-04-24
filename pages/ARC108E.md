---
title: "ARC108E"
---

from [[ARC108]]
[E - Random IS](https://atcoder.jp/contests/arc108/tasks/arc108_e)
![image](https://gyazo.com/455722a2c76a9cb48d1f29febf4ea080/thumb/1000)
- Untouched during the contest
- Thoughts.
    - For example, if you have 1,4,2,3 and you choose 4 first, you cannot choose 2 or 3.
    - If you divide the cases from the end by "if you choose, if you don't choose", you get 2^2000.
        - Is it too subtle to decide off the top of your head because even if you don't choose one, you will eventually have to choose one?
        - Need to find an extremely monotonically increasing sequence?
    - Decide from the smallest instead of the first?
        - different-looking
    - Maybe a change in the order of addition...
            - [The expected value of the sum is the sum of the expected values.
        - The "final selection" for each number is "whether the number to the left of you that is greater than you is selected before you."
        - Can I consider 1/(1+x) when there are x large numbers left in total?
        - Not good, when 4,2,3, the probability of 2 being chosen is 2/3 instead of 1/2
            - Because when 3 is chosen, 4 can't be chosen.
- Official Explanation
        - [[Interval DP]]
    - I couldn't come up with this as a section DP at all.
        - [[Section DP to be divided into]]
        - [[Expected DP]]

---
This page is auto-translated from [/nishio/ARC108E](https://scrapbox.io/nishio/ARC108E) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
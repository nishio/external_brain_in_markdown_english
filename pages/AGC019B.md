---
title: "AGC019B"
---

[B - Reverse and Compare](https://atcoder.jp/contests/agc019/tasks/agc019_b)
- ![image](https://gyazo.com/0f9d4abc0da3abe12d279a7e8d78c384/thumb/1000)
- Thoughts.
    - Should we separate them by length even or odd?
    - If we fix the center and expand the range, the new range will be doubled if the letters are different, and doubled if they are not different.
    - Still, that's not very efficient at all.
    - I'm surprised it's not "answer the remainder" when there are 200,000 characters.
    - DP to make the range a defined area?
        - If two pairs of letters are different, the number of cases is +1 for all ranges that include the pair of exchanges.
    - Ha, the inclusion-elimination principle?
        - No, you can't narrow it down by symmetry, so no.
- Official Explanation
    - Strings made up of two different kinds of characters at both ends can never match each other
            - [[Conditions under which the results of an operation are identical]]
            - ![image](https://gyazo.com/a6db0731133b26e95552e75a13baa401/thumb/1000)
                - [[Counting up what is X -> if X?]]

    - If you notice this, [[have an after-event]] turns into "count the number of matching pairs"
    - This is obtained by [Frequency→Triangular number
- problem partitioning
        - [[Update column ranges]]
        - [[Counting up the results of an operation]]


---
This page is auto-translated from [/nishio/AGC019B](https://scrapbox.io/nishio/AGC019B) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "arc060 a"
---

from  [[Typical ideas for coming up with solutions in competitive programming]]
arc060_a
[https://atcoder.jp/contests/arc060/tasks/arc060_a](https://atcoder.jp/contests/arc060/tasks/arc060_a)
- 2^50, so it's impossible.
- Is it better to loose than to determine if it matches A for 2^50 streets?
- A is given, so subtract A for now [[classify by sign]].
    - But even 2^25 is a tough call, and the worst case is 2^49.
- It is hard to find the sum for 2^49, but the value range is at most 50 x 49, so let's do [[exchange of value range and definition range]]!
    - I hope we can make it sum to frequency, [[frequency table]].
- If we take the bottom frequency table as L, the top frequency table as U, and the number of zeros as Z, then Li x Ri x 2^Z.
        - [[Cross-checking of two frequency tables]]
    - To be -1 because it includes cases where no one card is selected.
- computational complexity
    - Split by sign with N
    - Make a frequency table with DP in N^3
    - Frequency table butt-join with N^2
- Official Explanation
    - The move to reduce the order was to make the objective "sum to zero" by drawing A, regardless of the number of cards
    - I counted the "sum to zero" by comparing the two frequency tables, but the official solution is to DP them together and look at the point where the sum reaches zero.

---
This page is auto-translated from [/nishio/arc060 a](https://scrapbox.io/nishio/arc060 a) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
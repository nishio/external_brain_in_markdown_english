---
title: "cf17_final_C"
---

[C - Time Gap](https://atcoder.jp/contests/cf17-final/tasks/cf17_final_c)
- ![image](https://gyazo.com/01e359885c614aec1e69d08ebbe5252b/thumb/1000)
- Thoughts.
    - Cannot be greater than min of input
    - Time difference is up to 12
    - From the condition of being an integer, there are only 13 possible values
    - Three identical values are 0
    - 0 with two 12s.
    - One zero is zero.
    - If two values are the same, the difference between them cannot be greater than min
    - If we assign different values to those that have two, and search for those that have only one in each of the two ways, the worst case scenario is 2^12, so clearly there is room for more!
    - Summary, N increases to 50, but the key is to keep the number of searches required small.
- Official Explanation
    - Assumed solution by the above
    - Alternative solution: linear order if it can be shown that the solution alternately assigned to the left and right is optimal

[[cf17_final]]

---
This page is auto-translated from [/nishio/cf17_final_C](https://scrapbox.io/nishio/cf17_final_C) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "ABC175D"
---

from [[ABC175]]
ABC175D
[D - Moving Piece](https://atcoder.jp/contests/abc175/tasks/abc175_d)
![image](https://gyazo.com/d6e26e7f39e5bc1e3744dfaed3a30560/thumb/1000)
- K is 10^9, so O(K) looks tough too.
        - [[iterative square law]] and assumed O(log K)
        - The end point and score are given for one step forward from a certain starting point.
        - Given the endpoint and score for n steps, the endpoint and score for 2n steps can be easily obtained
        - If we calculate from 2^1 steps to 2^30 steps about 30 * N times, we can calculate the score by O(log K) for K less than 2^31
- This question was not "score after K times" but "maximum score under K times".
- When the time was almost up, I realized that it was a [[loop detection]], but I couldn't get to it in time.
        - [[Loop detection instead of doubling]]
- cause
    - Within a negative loop the maximum score can be negative
        - And yet you set the initial value to 0.
    - One max was inside the loop to calculate the maximum score (TLE).
    - If the positive loop just goes around at K, the not much is 0, but the score may actually be higher if it does not go around the last full circle
        - If you have a negative score, you should avoid that.
        - The official explanation below is False
            - > If we decide to try all the "remainder" parts of this cycle, it is optimal to use as much as we can when the sum of the cycle is positive and not use it at all when it is not.
- [AC](https://atcoder.jp/contests/abc175/submissions/16163877)

---
This page is auto-translated from [/nishio/ABC175D](https://scrapbox.io/nishio/ABC175D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
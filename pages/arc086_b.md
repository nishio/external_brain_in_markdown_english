---
title: "arc086_b"
---

[https://atcoder.jp/contests/arc086/tasks/arc086_b](https://atcoder.jp/contests/arc086/tasks/arc086_b)
- Build it.
- It doesn't have to be the shortest.
- Is there a case where it needs to be done 2N times?
    - 6,5,4,3,2,1 all exceed if you try to meet the condition with only +1, but we don't do that.
    - Is it OK to add the smallest number that is greater than or equal to the first to the second...and so on?
        - O(NlogN)
    - N is quite small at 50
        - A larger algorithm with more orders?
- Official Explanation
    - I thought it was tricky that the updated number was used instead of the original number, but rather take advantage of it
    - If the signs are aligned, the cumulative sum can be used.
        - I didn't notice that.
            - [[Cumulative sum of positive numbers is monotonically increasing]]
        - [[make the sign (line) matching the sign (e.g. of a bell, cheque, etc.)]] can be done under N

---
This page is auto-translated from [/nishio/arc086_b](https://scrapbox.io/nishio/arc086_b) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
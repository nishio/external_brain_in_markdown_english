---
title: "ABC165E"
---

[E - Rotation Matching](https://atcoder.jp/contests/abc165/tasks/abc165_e)
- ![image](https://gyazo.com/433122aabc060c44d595f84db3aff948/thumb/1000)
- Thoughts.
    - The point is, the difference can't be the same.
    - No K and N-K either.
    - I don't know how many assignments would be OK.
        - M must be less than N/2
        - Oh, it says > $M \times 2 + 1 \le N$
    - ![image](https://gyazo.com/72626eebb3eb1c72e900d7e5f7afa66a/thumb/1000)
        - Now if N is odd, the rest are even, so they're all guaranteed to be at different intervals.
    - This doesn't work when N is even, the rest of the numbers are also odd and covered.
        - Looks good if you shift one half.
        - If M is even, the length taken in the M/2nd and the remaining length match, so we spread 1 there.
        - After that, they will all be even numbers, so they won't be covered.
    - I'm sure there's a bug that could cause a discrepancy of 1 or so at the boundary, but it's better to implement it and squash it with a small test case than to think about it in my head.
- Official Explanation
    - Style that creates both odd-length and even-length clumps
        - The length, not the evenness, prevents overlap.


---
This page is auto-translated from [/nishio/ABC165E](https://scrapbox.io/nishio/ABC165E) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
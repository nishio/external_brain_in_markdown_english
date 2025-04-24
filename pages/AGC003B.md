---
title: "AGC003B"
---

[B - Simplified mahjong](https://atcoder.jp/contests/agc003/tasks/agc003_b)
- ![image](https://gyazo.com/3776cb4be722fd46b0626492d7a6a6c3/thumb/1000)
- This paragraph, the question read wrong.
    - Thoughts.
        - This is a maximum two-part matching because the even-oddness of the pair is different, and a pair is a matching of a bipartite graph.
        - But I'm not sure if it's safe to have 10^5 vertices.
        - If you have multiple cards with the same number, you can simply increase the capacity.
    - Official Explanation
        - There is a linear order solution.
        - I still don't get the maximum two-part matching.
            - [[Dinic]] was no good because O(V^2E)
- I realized I read the problem wrong.
    - Since the absolute value of the difference is "less than or equal to 1", it is a pair even when the difference is 0.
        - It's fundamentally wrong to use an even-odd, two-part graph.
    - Based on this, I'm thinking from the small side.
        - Up to three clumps have the same result no matter how they are taken.
        - When four, there is a pattern of loss when taken vertically (left).
        - ![image](https://gyazo.com/f9ca41f0dc1100449c1b4af2a65967c0/thumb/1000)
        - So should we always prioritize taking it sideways? There's a counterexample to that too, at 6 (right).
        - Bad behavior common to both patterns: "There are cards that are isolated to one once the left-most pair is taken."
        - So is it OK if you "pack and take from the edges so that nothing is isolated"?
            - I should be able to prove that this is OK, but if I'm in a contest, I'll implement it and try it out in a test case.
            - Official Explanation: When the number of sheets is divided into non-zero intervals, it can be shown that there is no better way to get the maximum value than the above method, with at most one sheet left over.
    - [[fill in the blanks (at the end of a task)]]

---
This page is auto-translated from [/nishio/AGC003B](https://scrapbox.io/nishio/AGC003B) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
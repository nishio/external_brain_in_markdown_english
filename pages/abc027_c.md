---
title: "abc027_c"
---

[https://atcoder.jp/contests/abc027/tasks/abc027_c](https://atcoder.jp/contests/abc027/tasks/abc027_c)
- Thoughts.
    - I wonder if using Grundy numbers when thinking about these problems improves the outlook.
    - In binary notation, we shift one bit every turn, so the timing when the number of digits exceeds that of N will come rather soon.
    - For example, at 100, you are sure to finish after 3 turns, and you don't want to lose an odd number of moves, so you terminate one turn early by incrementing on the first turn.
        - Unavoidable on an even number of moves
    - In the case of 110, the odd number of moves cannot exceed even if the odd number of moves increments, and the even number of moves does not cooperate, of course.
    - At 1000, it takes 4 turns to finish, and on an even number of moves, I don't want to lose, so I'll just increment appropriately and finish a turn early.
    - So, when N is n digits, the basic rule is to finish in n turns, so the side that doesn't like it can make it larger than N by incrementing it to see if it can finish one turn earlier.
    - The losing side must set all of its bits that are 1's in N to 1, and then set at least one 0 to 1.
    - The winning side can set the bit that is 1 in N to 0. If this is left of the bit that is 1 above, the opponent's turn cannot be greater than N.
- Official Explanation OK
    - To summarize, "the number of digits in the binary notation of N determines which player wants to increase the number, and once that is known, a log N step simulation will provide the answer."

---
This page is auto-translated from [/nishio/abc027_c](https://scrapbox.io/nishio/abc027_c) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
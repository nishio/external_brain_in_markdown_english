---
title: "code_festival_qualB_C"
---

[C - Alchemist](https://atcoder.jp/contests/code-festival-2014-qualb/tasks/code_festival_qualB_c)
- ![image](https://gyazo.com/af3c304e49c0ad7075a784961cdcaf35/thumb/1000)
- Thoughts.
    - Well, the order of the strings doesn't matter, so they'll be in the frequency table first.
    - About each character
        - If the supply at S1 is less than the demand, the difference must be taken from S2. The reverse is also true.
        - Accumulate this "number of letters to take" and if it exceeds N, NG
        - If it doesn't exceed, how can you say it's OK?
            - I can't think of any particular counterexamples...
        - If not exceeded, it means that the remaining letters are either in S1 or S2 and can be taken from either.
            - So OK.

- No official commentary

---
This page is auto-translated from [/nishio/code_festival_qualB_C](https://scrapbox.io/nishio/code_festival_qualB_C) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
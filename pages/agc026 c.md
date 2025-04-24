---
title: "agc026 c"
---

from  [[Typical ideas for coming up with solutions in competitive programming]]
agc026_c
[https://atcoder.jp/contests/agc026/tasks/agc026_c](https://atcoder.jp/contests/agc026/tasks/agc026_c)
- Thoughts.
    - How much does 18C9 cost...
            - [[Estimating computational quantities]]
        - I can afford 13, and 15 is too much to ask for, so 18 is a no-go.
        - Added: It was 36C18.
    - You can always assume that the number is even and the left end is red (since there is always a red-blue inverted one).
- Official Explanation
    - I see, [[Principle of 10 coins]].
        - Since the blue letters are N and the right half is also N, we can say "the number of blue letters on the left matches the number of red letters on the right".
    - If you halve it, you get 2^18, which is okay if you do a full search.
        - A kind of [[half-full enumeration]]?

---
This page is auto-translated from [/nishio/agc026 c](https://scrapbox.io/nishio/agc026 c) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
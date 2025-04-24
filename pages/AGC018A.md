---
title: "AGC018A"
---

[A - Getting Difference](https://atcoder.jp/contests/agc018/tasks/agc018_a)
- ![image](https://gyazo.com/783c32fab84daa98daab8903533862f0/thumb/1000)

- Thoughts.
    - You can't make 1 when everything is even.
    - If there is a pair whose greatest common divisor is n, then n can be made.
    - The ball you used is also returned, so once again, if you subtract n from the largest number m, you can make all multiples of n less than or equal to m.
        - There are cases where this m is not a multiple of n.
        - If n is not 1, then find the largest ball for every remainder of mod n
- Official Explanation
    - This is a mistake.
        - > There are cases where this m is not a multiple of n.
        - Because we're looking for a public commitment.
    - Policy is OK.

---
This page is auto-translated from [/nishio/AGC018A](https://scrapbox.io/nishio/AGC018A) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "ABC121D"
---

[D - XOR World](https://atcoder.jp/contests/abc121/tasks/abc121_d)
- ![image](https://gyazo.com/50b60f8288036da81264d8bbcaa20095/thumb/1000)
- Thoughts.
    - If you think about each bit individually, you can figure out the number of 1's in the interval by the remainder of the power of 2, right?
- Official Explanation
    - It is a logarithmic order solution
    - Constant order if you notice the following
    - $f(A, B) = f(0, A - 1) \oplus f(0, B)$
            - [[Arbitrary interval is the difference between intervals from 0]]
    - $2n \oplus (2n+1) = 1$
            - [[XOR of an even number and the next odd number is 1]]

---
This page is auto-translated from [/nishio/ABC121D](https://scrapbox.io/nishio/ABC121D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "AGC036A"
---

[A - Triangle](https://atcoder.jp/contests/agc036/tasks/agc036_a)
- ![image](https://gyazo.com/00c2a55af4f2c2390acec060dac38f9c/thumb/1000)

- Thoughts.
    - First, I thought of the largest triangle required, then I thought of one smaller triangle from that.
    - ![image](https://gyazo.com/0c706bc7c10cbf0775ba87d6ea6b2def/thumb/1000)
    - Generalizing, (0, 0), (1, 10^9), (10^9, i) for 0 <= i <= 10^9 can express 10^18-i
    - What about something even smaller than that?
        - (0, 0), (1, 10^9 - j), (10^9, i) can represent 10^18 - j * 10^9 - i
- Official Explanation
    - exactly the same

---
This page is auto-translated from [/nishio/AGC036A](https://scrapbox.io/nishio/AGC036A) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
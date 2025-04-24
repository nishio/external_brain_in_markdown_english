---
title: "Watchdogs up and down the range"
---

I want to handle out-of-range accesses of `[0, N)` in [[dynamic programming]], such as accesses in the range i-1, i, i+1, with [[guard]].

→ In Python, you can use `table = [INF] * (N + 1)`.

Because `table[-1]` means `table[N]`.
---
This page is auto-translated from [/nishio/範囲上下に番兵](https://scrapbox.io/nishio/範囲上下に番兵) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
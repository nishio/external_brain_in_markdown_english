---
title: "Relationship between sigmoid and softmax"
---

from [[x/(x+1)]]
Relationship between sigmoid and softmax
- $\sigma(s) = 1 / (1 + \exp(-s))$
- $m(x_i) = \exp(x_i) / \sum \exp(x_i)$
- $\sigma(s) = \exp(s) / (\exp(s) + \exp(s)\exp(-s)) = \exp(s) / (\exp(s) + 1) = \exp(s) / (\exp(s) + \exp(0))$
In other words, the sigmoid is a two-factor softmax, which corresponds to the case where the output of the event of interest's extra-event is 0

---
This page is auto-translated from [/nishio/シグモイドとソフトマックスの関係](https://scrapbox.io/nishio/シグモイドとソフトマックスの関係) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "cross entropy"
---

- Cross entropy when p, q are discrete probability distributions:.
- $H(p,q) = -\sum_x p(x) \log q(x)$
    - x corresponds to a class in the context of multiclass classification
- When x is {0, 1}:.
- $H(p, q) = -\{ p(0)\log q(0) + p(1)\log q(1) \}$
- Since the probability of being 0 and the probability of being 1 add up to 1
- $H(p, q) = -\{ (1 - p(1))\log (1 - q(1)) + p(1)\log q(1) \}$
- Rewriting the probability of p being 1 as t and the probability of q being 1 as y
- $H(p, q) = -\{ (1 - t)\log (1 - y) + t \log y \}$

### Much of the confusion about cross entropy and log loss is due to the ambiguity about what the sum is about
.
- As above, with the assumption that x runs a class, the following holds for a 2-class classification
- $-\sum_x p(x) \log q(x) = -\{ (1 - t)\log (1 - y) + t \log y \}$
- If we want to calculate the sum of the loss of all data under the assumption that i runs each data, the following holds. (Just wrap the above equation with sum_i)
- $-\sum_i \sum_x p(x) \log q(x) = -\sum_i \{ (1 - t)\log (1 - y) + t \log y \}$
- It is pointless to confuse the two and compare the two below side by side.
- $-\sum_x p(x) \log q(x)$
- $-\sum_i \{t \log y + (1 - t)\log (1 - y)\}$
- Cross entropy and log loss are the same!" and equating the above two equations with the expression "Cross entropy and log loss are the same!
---
This page is auto-translated from [/nishio/クロスエントロピー](https://scrapbox.io/nishio/クロスエントロピー) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
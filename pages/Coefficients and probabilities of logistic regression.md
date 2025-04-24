---
title: "Coefficients and probabilities of logistic regression"
---

- Logistic regression $P(y|X) = \sigma(W^tX)$.
- Definition of sigmoid $\sigma(ax) = \frac{1}{1 + \exp(-ax)}$
- As for probability, it is an [[S-shape]] curve, so an increase in the coefficient does not increase the probability by a factor of
- Consider odds p / (1 - p)
- $\frac{p}{1 - p} = \frac{\frac{1}{1 + \exp(-ax)}}{1 - \frac{1}{1 + \exp(-ax)}} = \frac{1}{(1 + \exp(-ax)) - 1} = \frac{1}{\exp(-ax)}$
- So the odds are e times lower when the coefficient increases by one.
---
This page is auto-translated from [/nishio/ロジスティック回帰の係数と確率の関係](https://scrapbox.io/nishio/ロジスティック回帰の係数と確率の関係) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
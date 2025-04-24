---
title: "Thompson sampling"
---

- [[Theory and Algorithms for the Bandit Problem]]  p.38  [[Thompson extraction]]
- Bayesian estimation] of expected value
- Choose the action with the probability of being the maximum expected value of each action ([[random dither]])
- However, instead of doing this "probability of being the maximum expected value" calculation, use the [random-choice algorithm
- Since it is Bayesian, a distribution of expected values is obtained. Sampling from this distribution
- Select the action that had the largest value as a result of sampling
- This will make it possible to "choose that action with the probability of being the maximum expected value.

[https://hagino3000.blogspot.com/2015/07/thompson-sampling.html](https://hagino3000.blogspot.com/2015/07/thompson-sampling.html)
[https://hagino3000.blogspot.com/2016/12/linear-bandit.html](https://hagino3000.blogspot.com/2016/12/linear-bandit.html)

#Reinforcement Learning

---
This page is auto-translated from [/nishio/トンプソンサンプリング](https://scrapbox.io/nishio/トンプソンサンプリング) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
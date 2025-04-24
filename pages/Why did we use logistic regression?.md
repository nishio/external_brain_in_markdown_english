---
title: "Why did we use logistic regression?"
---

- Parking difficulty determination function by [[machine learning]] by Google
    - [Research Blog: Using Machine Learning to Predict Parking Difficulty](https://research.googleblog.com/2017/02/using-machine-learning-to-predict.html)
    - Using [[logistic regression]] instead of the popular Deep Learning
    - It explains why.

- reason
    - Easy to understand behavior (unlike Deep Learning, etc.)
    - Highly resistant to noise
        - This feature is convenient because the data comes from crowdsourcing.
    - Since it is a stochastic model, it is natural to interpret output values as probabilities
        - As a result, it is easy to map output results to human-understandable descriptions (e.g., "easy parking")
    - It is easy to understand how much influence the features have on the results.
        - This makes it easy to verify that the model is working properly.
        - For example, a prior hypothesis that a certain complex feature would be useful in solving a problem was rejected by the actual data.
        - Some of the simpler features were found to be beneficial

Related: [[Technologies used by data scientists around the world]] Data showing that logistic regression is common
---
This page is auto-translated from [/nishio/なぜロジスティック回帰を使ったか](https://scrapbox.io/nishio/なぜロジスティック回帰を使ったか) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
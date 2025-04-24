---
title: "Add 2 to the denominator and 1 to the numerator"
---

- The distribution of the two sides of a coin (independent trials that come out heads with probability p) is called the "[[Bernoulli distribution]]".
- The [[conjugate prior distribution]] of the Bernoulli distribution ([[prior distribution]] convenient for [[Bayesian update]], Kyoyaku~) is a [[beta distribution]].
- The probability distribution after an observation is made is called [[posterior distribution]].
    - Bayesian, it can be derived from the prior distribution and observed facts by computing it using [[Bayes' law]].
- The estimation method in which the [[mode]] of the posterior distribution is chosen to be the [[estimated value]] is called [[MAP estimation]] ([[Maximum posterior probability estimation]]).
- There is no reason why the mode should be chosen as the [[point estimate]] when the distribution is obtained, so it can be estimated with [mean value
    - [Mode of beta distribution
    - ![image](https://gyazo.com/56a931b048b951464e9fdc9c819e3ec2/thumb/1000)
- The average value ([[expected value]]) is
    - ![image](https://gyazo.com/4f515d445ece206476f50d00a3351c33/thumb/1000)
- Beta distribution becomes [[uniform distribution]] when α=β=1.
- when the prior distribution is a beta distribution B(α, β),
    - After one observation of the table, the posterior distribution becomes B(α+1, β)
    - The posterior distribution after one observation of the backside is B(α, β+1)
- So, after first assuming a uniform distribution as [[uninformed prior distribution]] and then observing the front side A times and the back side B times, the probability p of getting the front side is
    - Mode A/(A+B)
    - Average (A+1)/(A+B+2)
- That is, [[MAP Estimates]] becomes [sample mean
    - In this case, for example, when a coin is tossed only once and a table is observed only once, "This coin will turn up with probability 1!" and estimate
    - This kind of conclusion is not good ([[overlearning]]).
    - So we'll use the mean of the posterior distribution, which gives more moderate results.
        - On average, I would estimate that "this coin has a 2/3 chance of showing up".
        - [[sample]] Converge to the same value as the number increases
- For this reason, the estimation method "add 2 to the denominator and 1 to the numerator" is used when estimating p for the Bernoulli distribution
---
This page is auto-translated from [/nishio/分母に2を足し、分子に1を足す](https://scrapbox.io/nishio/分母に2を足し、分子に1を足す) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Risks and Vulnerabilities"
---

Anti-Fragility Study Group
- The book [[antivulnerability]] was discussed
- How do you define antifragility?"
- Organize the knowledge on which the discussion is based

    - How to quantify the size of [risk
        - [[standard deviation]]
        - $\sqrt{\mathbb{E}[(X-\mu)^2]}$
        - $\sqrt{\sum (x - \mu)^2 P(X=x)}$
        - No change Zero
        - 10,000 is either 0 or 20,000.
            - Standard deviation 10,000 yen
        - lottery
            - Example: 1/20 million chance of 700 million yen
                - Ignore other minor awards because the math is too tedious.
                - Expected value 35 yen
                - 1/2 billion chance of -$700 million -$35 plus, -$265 for the rest of the probability.
                - sqrt(2.45e9 + 70225)
                - Standard deviation is about 50,000 yen
                    - It's like betting 50,000 becomes 0 or 100,000.
                    - In general, they say the expected value is about $150, with a standard deviation of about $160,000.
        - reverse lottery
            - A gamble that gives you $300 but takes $700 million with a probability of 1/20 million.
            - This, of course, has the same degree of risk.
        - [[downside risk]]
    - $\sqrt { \mathbb{E}[(X-\mu)^{2}]1_{\{X\leq\mu\}} }$
    - $\sqrt{\sum (X - \mu) ^2 1_{\{X\leq\mu\}}}$
        - Incorrect: $\mathbb{E}_{\{X\leq\mu\}}[(X-\mu)^{2}$]
            - I was wrong.
        - In general, we discuss not only $\mu$, but also the downside risk when the point of interest k is defined
        - The downside risk of lottery tickets is...
        - The downside risk of betting 50,000 becomes 0 or 100,000...
        - The downside risk of a reverse lottery is...
        - The lower you go, the bigger it gets.
        - Synonyms: [[upside risk]].

- Concept of BETA
    - Some random variable X and a random variable Y
    - $Y = \alpha + \beta X + \epsilon$
    - at this time
    - $\beta = \frac{Cov(X, Y)}{Var(Y)}$
- Assume base asset X is a stock.
    - If you borrow money and buy 10 times the amount of stock, BETA will increase by about 10 times.
        - So-called "[[leverage]]"
    - Is that calculation really the right one? I'm beginning to wonder.
    - [Long Term Capital Management - Wikipedia [https://ja.wikipedia.org/wiki/%E3%83%AD%E3%83%B3%E3%82%B0%E3%82%BF%E3%83%BC%E3%83%A0%E3%83%BB%E3%82%](https://ja.wikipedia.org/wiki/%E3%83%AD%E3%83%B3%E3%82%B0%E3%82%BF%E3%83%BC%E3%83%A0%E3%83%BB%E3%82%) AD%E3%83%A3%E3%83%94%E3%82%BF%E3%83%AB%E3%83%BB%E3%83%9E%E3%83%8D%E3%82%B8%E3%83%A1%E3%83%B3%E3%83%88]
        - High investment performance was achieved, but this was due to leverage
- It is now being discussed whether it might be better to think about downside with respect to this Variance as well.
    - →The emergence of the concept of downside beta

- The concept of volatility
    - Standard deviation with fixed time horizon
    - I thought about the standard deviation "after the winning numbers are announced" in the discussion of lottery risk.
    - Often the context assumes a change in the option price.
        - Consider "the distribution of prices after a certain number of days" since prices fluctuate continuously on a daily basis.
    - Often write $\sigma$.

- vega concept
- $\frac{\partial V}{\partial \sigma}$
    - Option price differentiated by volatility
    - For example, when considering an option transaction that says, "I will give you 10,000 yen if the price in one month's time is within 10% of the current price, but I will take 10,000 yen if it is not," the higher the volatility of the underlying asset, the lower the price of this option.
        - → negative vega
    - stock option
        - Option to exchange "the right to earn X shares in the future" for a current cash salary of 1,000,000 yen.
        - If the stock becomes a piece of paper - 1,000,000 yen
        - If the price of X share is 2 million, +1 million
        - The higher the volatility, the higher the expected value (because it does not go below 0).
            - Stock options increase in value.
        - → positive vega
    - Cybozu's Shareholding Association
        - Option to earn 2X shares of stock at the present time in exchange for X amount of cash at the present time
        - If the stock price does not change, +X yen
        - If the stock price goes up, well, I'll be happy.
        - Losses if the stock price drops below half its original price.
        - Ignoring the probability of going from the current price to zero, the expected value remains the same.
        - What are the option prices?
        - The higher the volatility, the lower the [[risk premium]].
        - → negative vega

- What is Fragility?
    - It is a left-side vega
    - In other words, the same composition as "risk -> downside risk" and "beta -> downside beta" is used for vega.
    - Reverse lottery example
        - Risks that are not downside could not distinguish between "mostly gains but very rarely large losses" and "mostly losses but very rarely large gains".
    - Similarly, can't a non-downside vega handle the very rare "very high volatility conditions" (base asset spikes and crashes) well?
    - left-side means that the downside is to the left when the probability distribution is drawn with the target value on the X-axis.

- What is ROBUST?
    - Less fragility?
    - We're talking about distribution shape stability.

- What is antifragility?
    - > Antifragility is not the simple opposite of fragility, as we saw in Table 1. Measuring antifragility, on the one hand, consists of the flipside of fragility on the right-hand side, but on the other hand requires a control on the robustness of the probability distribution on the left-hand side. From that aspect, unlike fragility, antifragility cannot be summarized in one single figure but necessitates at least two of them.
    - Fragility (downside vega) folded to the right and Robustness combined concept

---
This page is auto-translated from [/nishio/リスクと脆弱性](https://scrapbox.io/nishio/リスクと脆弱性) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
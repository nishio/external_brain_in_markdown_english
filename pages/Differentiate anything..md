---
title: "Differentiate anything."
---

[https://speakerdeck.com/joisino/he-demowei-fen-suru](https://speakerdeck.com/joisino/he-demowei-fen-suru)
- If [[optimal transport]] is viewed as an optimization problem, it is not [differentiable
    - cannot be solved by the [[gradient method]] because
- But with a good [[regularization term]] you can do it.
    - ![image](https://gyazo.com/6cac326261527a446755574a8eaf5881/thumb/1000)
    - Can be calculated with [Sinkhorn Algorithm
        - And it can be [[automatically differentiated]].
            - and can be combined with other auto-differential algorithms such as NN
- [[Ranking Study]]( [[Ranking Study]] )
    - Optimization of the percentage of correct answers
        - Correct rate is not differentiable because of the step function that is included.
            - The term [[cross entropy]] has been customarily used because
                - However, there would be an incentive to renew even for "questions already answered correctly".
                    - Associations: [[Passive-Aggressive]].
    - [[The ranking problem is a one-dimensional optimal transport problem]].
- Various processes can be made differentiable.
    - [[Ranking]], [[Sort]], [[Beam Search]].
    - General [[linear programming problem]] can also be solved by [Bregman method
            - The [[gradient method]] such as [[Adam]] can be used to solve the [[shortest path problem]].
    - Can be put in [end-to-end optimization

Contact: @joisino_ (Twitter) / [https://joisino.net/](https://joisino.net/)
[[joisino]]

---
This page is auto-translated from [/nishio/何でも微分する](https://scrapbox.io/nishio/何でも微分する) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
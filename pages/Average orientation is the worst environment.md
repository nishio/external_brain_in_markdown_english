---
title: "Average orientation is the worst environment"
---

2017-11-27
It would be interesting if [[mathematic model]] could express the difference between the environment where the average is optimal and the environment where the average is the worst.

Results of 100,000 experiments
- Under the condition that the top 70% receive the reward, those who followed the strategy of making their behavior closer to the average of the observed behavior of others (average-oriented strategy) had an 85% chance of receiving the reward, whereas those who followed the strategy of changing their behavior away from the average (anti-average-oriented strategy) had a 60% chance of receiving the reward.
- Conversely, under the condition that the top 30% receive compensation, the average-oriented strategy was 15%, while the anti-average-oriented strategy was 40%.

in other words
- If a majority of people receive compensation, it is more advantageous to take an average orientation
- Otherwise, it is more advantageous to move away from the average
    - In [[school education]], [[average-orientation]] is advantageous because a majority of students advance to the next grade and a few fail.
- In society, [[anti-average orientation]] is advantageous because in [[competitive situations]], the majority of people do not win and a few people win
- Related [[How to come up with good ideas]].

How it all started [ochyai](https://twitter.com/ochyai/status/933471607837753344) [[Yoichi Ochiai]]
- > The reactions to Jounetsu Tairiku make me think that there are many people who live their lives thinking that "[[usually]]" is "the truth of the Heavens, the Earth, and the Divine. [Average is not optimal.
- > Innovation changes costs, culture and attitudes. Flexible trial and error is necessary, but as a result of current education, many people lack the principles and motivation to base their decisions on.
    - [[Can you spot innovative talent in advance?]]


We thought it would be interesting if a mathematical model could express the difference between an environment where the average is optimal and an environment where the average is the worst.

modelling (e.g. a system, etc.)
- There are n agents.
- Each agent has a D-dimensional "action vector". This shall represent their behavior.
- Initially, the action vector follows a normal distribution
- Each agent can observe the behavior of others
    - There are many design options for how to make it observable, but we'll make it observable with probability p
    - It would be interesting to design a system where only people close to the action can be observed.
- Each agent can modify his or her own behavior based on observations of others' behavior
    - There are also design options on how to fix it.
    - In this case, "Find the average value of the observed information and update your behavior in the direction of moving closer/further away from that average".
    - It would be interesting to see the median instead of the mean and the shape of the distribution.
    - If the action is a, the mean is m, and the learning rate η is 0.5 or -1:.
    - $a_{new} = a + \eta (m - a)$
- A random vector is chosen as the evaluation axis, and rewards are given to q * N participants in descending order of value along the axis.
    - Image of "Reward the top 10%"
    - Setting q = 90% also creates a situation where "disadvantages are given to the bottom 10% of grades".
    - I think this nonlinearity is the key, but it would be interesting to experiment with changing it.
- Run this experiment 100,000 times and observe how the probability of receiving a reward changes with behavior modification strategies

p=0.5, eta=0, 0.5, -1.0:

```
# q = 0.7
0.70119  0.84714  0.60523
# q = 0.3
0.29822  0.15266  0.39567
```


source
- [https://gist.github.com/nishio/d57e424dafa9b0bb2b86ed31468e0e6e](https://gist.github.com/nishio/d57e424dafa9b0bb2b86ed31468e0e6e)

---
This page is auto-translated from [/nishio/平均志向が最悪の環境](https://scrapbox.io/nishio/平均志向が最悪の環境) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
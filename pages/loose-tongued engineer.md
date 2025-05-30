---
title: "loose-tongued engineer"
---

summary
- Even if two attributes x and y are independent and uncorrelated, selection based on their sum will produce an inverse correlation

I saw a topic on Facebook about whether there is a correlation between a bad mouth and engineering ability and thought, "That can be explained with a mathematical model," so I wrote about it.

First, suppose an engineer has two abilities, x and y. For example, you may think of x as a good mouth and y as a programming ability.
Assuming that these two abilities follow a standard normal distribution, the distribution of all engineers would be as follows. There is no correlation between the abilities.
![image](https://gyazo.com/8673b7bdec64253813327fe3415127e3/thumb/1000)

So, there is an opportunity for [[selection]] in the world. Let us select 10 persons at random from the above distribution and choose only the person whose sum of ability x + y is the largest among them. The distribution of the selected persons will be as follows.
![image](https://gyazo.com/686eda5ffa9425ed9f25a360360945f1/thumb/1000)

The correlation coefficient is -0.46, which means that the smaller x is, the larger y is.
The average of the ability of the selected persons is about 1.1 each. In other words, in terms of deviation, it is about 61.
Despite being such a "highly capable group of people," there are those whose x is less than the all-engineer average of 0.
This may come as a surprise, but about 10% of those selected do.

The average skill of these "people whose x is worse than average" is (-0.37, 1.87), which is 46 and 69 in terms of deviation, which means that compared to the distribution of engineers as a whole, their y is much higher in exchange for a slightly worse x than average.

This inverse correlation is caused by multiplying a highly competitive selection by a factor of 10. For example, it is very possible that laboratories in highly competitive universities are in a similar situation, so that they are not well-spoken but have good programming skills.
On the other hand, if a person with a bad mouth visits for job hunting, that person has not gone through the selection process, or "those who won the selection process are employed without job hunting, and those who lost are job hunting because they are losers". Therefore, such a person should not be hired.

PS: Note that in this experiment, the selection was made based on the overall skill of x + y, and then we looked at the high and low y of those with low x.
Measured by the composite skill x + y, the average skill of the selected persons is 2.2, while the average skill of the outspoken persons is 1.5.
In other words, "In a situation where x is observable but y is not for a person selected based on overall skill, it is reasonable to take someone with low x if you want to hire someone with high y, but if you want to take someone with high overall x + y, you should honestly take someone with high x."

#mathematical model thinking #confluence bias #selection bias

#NecessaryExperiments
- In this model, x is observable and y is not in the interview.
    - This is not a very natural assumption. Some attributes are easily observable even in the limited time of an interview, while others can only be observed over time.
        - If we assume this to be, for example, "the value with noise can be sampled at regular intervals," the smaller the sampling interval, the faster the attribute approaches the correct value, and the same is true for the attribute with less noise.
        - Noise is uncorrelated with the value of the attribute, but in reality some people "deliberately make it appear less capable". [src [https://www.facebook.com/nishiohirokazu/posts/10214370581674925?comment_id=10214370848641599&comment_tracking=%7B%22tn%22%3A%](https://www.facebook.com/nishiohirokazu/posts/10214370581674925?comment_id=10214370848641599&comment_tracking=%7B%22tn%22%3A%) 22r4%22%7d]
            - This probably does not make everyone look equally less capable, but rather changes based on who they are dealing with.
            - If the utility of being valued by others is saturated and the cost of being valued by others (relationship maintenance cost) is not saturated, relationship building beyond a certain degree becomes cost-effective worse.
                - [[a wise man keeps some of his talents in reserve]]
- The problem of people who are intolerant of attribute x [src [https://www.facebook.com/ohkubo.kohei/posts/10155407243636476?comment_id=10155407455981476&reply_comment_id=](https://www.facebook.com/ohkubo.kohei/posts/10155407243636476?comment_id=10155407455981476&reply_comment_id=) 10155407497886476&comment_tracking=%7B%22tn%22%3A%22R2%22%7D]
    - Difference between cases where the organization is occupied by people who are not x-tolerant (when having a high x member among colleagues lowers utility) and cases where the organization is not x-tolerant.
    - So an organization occupied with people who are not tolerant of x will not value people who are high in x.
    - This is not a matter of who is to blame, but rather a characteristic of the organization, and people with high x did not match the organization, so people with high x can find another workplace.
    - Organizations that are more tolerant of x are more likely to hire people with high y
    - I think there is another axis "immunity z to bad mouth".
        - People with high z have no problem communicating with people with low x
        - People with low z are disadvantaged by communicating with people with low x
        - Maybe agent simulation will cause polarization #Experiment needed

---
This page is auto-translated from [/nishio/口の悪いエンジニア](https://scrapbox.io/nishio/口の悪いエンジニア) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
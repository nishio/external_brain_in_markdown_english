---
title: "Quadratic Voting: How Mechanism Design Can Radicalize Democracy"
---

[[Steven Lalley]], [[E. Glen Weyl]] (2018)
> Can mechanism design save democracy? We propose a simple design that offers a chance: individuals pay for as many votes as they wish using a number of "voice credits" quadratic in the votes they buy. Only quadratic cost induces marginal costs linear in votes purchased and thus welfare optimality if individuals' valuation of votes is proportional to their value of changing the outcome. A variety of analysis and evidence suggests that this still-nascent mechanism has significant promise to robustly correct the failure of existing democracies to incorporate intensity of preference and knowledge.
>
>  The online appendix for "Quadratic Voting: How Mechanism Design Can Radicalize Democracy" may be found here: [http://ssrn.com/abstract=2790624.](http://ssrn.com/abstract=2790624.)
[https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2003531](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2003531)
American Economic Association Papers and Proceedings, Vol. 1, No. 1, 2018
but the preprint was published in 2012.

2024-01-30
- Below are my notes from reading the 2023-07-20- "What the heck is this?" I'm not very organized.
- The more I understand, the more I feel it's an important concept.

from [[Quadratic Voting]]
Quadratic Voting: How [[Mechanism Design]] Can Radicalize Democracy
[https://www.researchgate.net/publication/325310987_Quadratic_Voting_How_Mechanism_Design_Can_Radicalize_Democracy](https://www.researchgate.net/publication/325310987_Quadratic_Voting_How_Mechanism_Design_Can_Radicalize_Democracy)
> Can mechanism design save democracy? We propose a simple design that offers a chance: individuals pay for as many votes as they wish using a number of "voice credits" in the votes they buy. Only quadratic cost induces marginal costs linear in votes purchased and thus welfare optimality if individuals' valuation of votes is proportional to their value of changing the outcome. A variety of analysis and evidence suggests that this still-nascent mechanism has significant promise to robustly correct the failure of existing democracies to incorporate intensity of preference and knowledge.
(DeepL+nishio) Can [[mechanism design]] save [[democracy]]`? We propose a simple design that offers that possibility. Individuals pay for as many votes as they wish, using the number of "voice credits" in the votes they purchase. If individuals' valuation of their votes is proportional to their value for changing the outcome, then only the quadratic cost yields a marginal cost that is linear in the number of votes purchased, resulting in a welfare optimum. Various analyses and evidence suggest that this still developing mechanism has great potential to robustly correct existing democracies' failure to incorporate preference strength and knowledge.`

- I don't like translating "quadratic" as "secondary" because it feels like a secondary nuance.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
    - In Taiwan, it seems to be "[[square vote]]", I prefer this one [Discord](https://discord.com/channels/1087587764691808316/1093884258231267499/1114087516870561912)

    - [[direct democracy]] as a prerequisite and an improvement on how to achieve it?
    - Is there only one agenda item for the "choose from multiple candidates who will be mayor" type of thing that many people associate with the word "vote"?
        - > Many two-option collective decisions (e.g., referendums, election of leaders) are made.
        - Encode the selection of leaders into a two-choice group decision as well?
    - Ah, I see, the premise is to change the right to vote from "something that disappears if not used in a particular election" to [[Speech tokens]] that have continuing value.
        - > As is common in the analysis of markets for private goods (Willig, 1976), we assume there are enough issues and that each is sufficiently inconsequential that every voter has a quasi-linear “continuation value” for retaining voice credits for future votes.
        - (DeepL) As is common in private goods market analysis (Willig, 1976), we assume here that there are a sufficient number of issues, each sufficiently inconsequential, that all voters have a quasi-linear "continuation value" that retains a say in future voting.
        - So possible future votes will be in scope and "multiple agenda items".
- The "one vote per agenda item" implicitly assumed "equality of [[attention]] to the agenda item," but that's not really the case.


<img src='https://scrapbox.io/api/pages/nishio-en/GPT-4/icon' alt='GPT-4.icon' height="19.5"/>As is common in market analysis of private goods (Willig, 1976), assume that there are enough issues, each sufficiently irrelevant, that every voter has a "[[Continued Value]]" that holds a say credit for future votes.
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>In today's general voting, voting credits are "tokens that lose value if not exercised at the time of the vote," but "[[Speaking Credits]]" in this paper have continuing value because they can be used for future votes.

- [[Why does Quadratic Voting take square roots?]]
![image](https://gyazo.com/790419420c09b9156f713bbfda589030/thumb/1000)
- In an existing two-option vote to choose A or B, voters can only vote +1 or -1
    - If the sum of them is greater than zero, A wins.
- As a result, the votes of the "Being an A is very important!" and "I don't care either way, but if I had to choose, I'd say B!" people's votes have the same power and cancel each other out.
    - Not good!
- So we want to allow voters to change the weight of their votes.
    - But if you can change it arbitrarily, people will make it infinitely stronger.
    - So introduce a structure where "it costs more to have a stronger voice".
    - This paper examines the conditions for the cost function c to have favorable characteristics in order to discuss how this cost should be
    - In conclusion, it is better to make it a quadratic function

<img src='https://scrapbox.io/api/pages/nishio-en/GPT-4/icon' alt='GPT-4.icon' height="19.5"/>In deciding how many votes to purchase, each voter compares the marginal cost of an additional vote with the probability that the vote is perceived to play a decisive role in influencing the outcome of the election. The price acceptance assumption we adopt, first proposed by Mueller (1973) and Laine (1977), is that all voters agree on the marginal determinacy p of their votes in this issue (although it may vary from issue to issue).
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>`marginal pivotality of votes p`
    - The assumption is made that everyone knows before purchasing a ballot that the acquisition of additional voting rights could change the outcome, and that everyone assumes the same value.
    - That's a pretty strong assumption.
    - If we accept that assumption, then a rational voter would choose the number of votes that maximizes [$ 2u_ipv_i - c(v_i)
- `robustly optimal` means that the signs of $\sum_i v^*_i$ and $\sum_i u_i$ match
    - for every p > 0, N and vector u, each price-taking voter i chooses votes $v^*_i$

[/blu3mo-public/Quadratic Voting#6435f5161286260000f30f6c](https://scrapbox.io/blu3mo-public/Quadratic Voting#6435f5161286260000f30f6c)
- > Is there a rationale for setting n=2...?
- Answer to this
- > THEOREM 1: A vote pricing rule is robustly optimal if and only if it is quadratic.
- If $2u_ipv_i - c(v_i)$ is maximized, then the derivative of it by v is zero
    - If we expand this, we see that u and v are proportional only when c is a quadratic function
        - ![image](https://gyazo.com/1bf407b0356839250026e6a178224c72/thumb/1000)

- Consideration of changing this a
    - If a=1, the cost of getting a new vote is constant.
        - In this case, it would be a dictatorship of the person with the highest absolute value of u
        - Because the value of this shoulder goes to infinity.
            - ![image](https://gyazo.com/cdf578f6c0eee5eac996f037d8ed75d8/thumb/1000)
    - If you set a to infinity, everyone votes for just one.
        - Just like a normal majority vote now.
    - a=2 is [[moderation]].
- relevance
    - [/tkgshn/why-quadratic-voting-is-squared](https://scrapbox.io/tkgshn/why-quadratic-voting-is-squared)
    - <img src='https://scrapbox.io/api/pages/nishio-en/Quadratic Payments: A Primer/icon' alt='Quadratic Payments: A Primer.icon' height="19.5"/>



---
This page is auto-translated from [/nishio/Quadratic Voting: How Mechanism Design Can Radicalize Democracy](https://scrapbox.io/nishio/Quadratic Voting: How Mechanism Design Can Radicalize Democracy) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
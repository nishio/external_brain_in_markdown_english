---
title: "Quadratic Voting and Plural Management Study Group"
---

[[Quadratic Voting]](QV) and [[Plural Management Protocol]](PMP) Study Session
- 2024-03-15  [[Cybozu Labs Study Session]]
- In the last [[Plural Management Study Session]], I read a freshly written paper on "Plural Management
    - > South, Tobin and Erichsen, Leon and Jain, Shrey and Maymounkov, Petar and Moore, Scott and Weyl, Eric Glen, [[Plural Management]] (January 9, 2024)
- As a result, I realized I should start with [[Quadratic Voting]].
- The following two stories are included in this issue
    - [[Quadratic Voting]]
        - > [[Quadratic Voting: How Mechanism Design Can Radicalize Democracy]]
        - > Steven Lalley, E. Glen Weyl (2012~2018)
    - [[Quadratic Funding]]
        - > [[Liberal Radicalism: A Flexible Design For Philanthropic Matching Funds]]
        - > Buterin, Vitalik and Hitzig, Zoë and Weyl, Eric Glen (2018)
    - Plural Management] if there is room.
- relevance
    - This is about [mechanism design
            - [[Mechanism Design Study Group]] / [[Majority Judgement Study Group]] (done in 2021)
        - I explained Majority Judgement (2007) at this time.
            - [[One vote per person is unnatural.]] by [[Toyotaka Sakai]] (a reference to QV by the author of a book read at a mechanism design study group)

Quadratic Voting
- Voting system designed to allow participants to express "strength of opinion"
- It's explained in Japanese books like [[radical market]].
    - Originally published in Radical Markets: Uprooting Capitalism and Democracy for a Just Society
        - [[Eric A. Posner]], [[E. Glen Weyl]](2018)
- When I say, "Let's allow people to express the strength of their opinions," what comes to mind naively is a five-point vote.
    - Make it five levels: "Strongly in favor," "Weakly in favor," "Neutral," "Weakly opposed," and "Strongly opposed."
- What's wrong with this?
- Since the cost of a "strong favor" and a "weak favor" are the same, in some cultures, "I don't see why a weak argument should exist."
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Explain how the distribution of votes differs from culture to culture when rated on a 5-point scale.
    - <img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>Cultural humility and self-expression
        - In high context cultures (e.g., Asian countries), people often value [[humility]] and tend to understate their own achievements and satisfaction. This may be reflected in a tendency to avoid extremely high or low ratings on a 5-point scale, preferring the middle option.
        - In low-context cultures (e.g., the U.S. and Western European countries), [[individualism]] is emphasized, and one is encouraged to clearly express one's opinions and accomplishments. This can lead to a tendency toward more extreme ratings ("1" or "5").
    - ![image](https://gyazo.com/196b0f1254fb49486d2291d5e1eab25b/thumb/1000)
            - [[radical market]]  p.175~176
            - >  [[Likert survey]] does not force respondents to be honest about the strength of their preferences, so respondents tend to exaggerate
        - This is an American story of low context culture.
- Now let's make sure that the stronger the claim, the higher the cost!
    - →What cost function is appropriate?
- [[Quadratic Voting: How Mechanism Design Can Radicalize Democracy]]
    - preprint(2012)
    - >  Can [[mechanism design]] save [[democracy]]? We propose a simple design that provides an opportunity: give each individual as many votes as they wish, but at a cost that is proportional to a quadratic function of the number of purchased votes. Only quadratic costs make the marginal cost linear with respect to purchased votes, and thus the valuation of individual people's votes is proportional to the value of the resulting change, yielding welfare optimality. Various analyses and evidence show that there is great promise that this still developing mechanism can robustly correct existing democratic failures and incorporate preference strength and knowledge.
- I like quadratic costs.
    - <img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>The main idea of Quadratic Voting is that each participant can purchase multiple votes and vote for the option he or she supports, but for each additional vote cast, the cost increases quadratically. That is, the first vote costs 1 unit, but it costs an additional 3 units to get a second vote (for a total of 4 units) and another 5 units to get a third vote (for a total of 9 units).
    - This is Quadratic Voting
- Why quadratic costs are good
    - I explained a bit about it earlier in [Why does Quadratic Voting take square roots?
    - As of 2012, the calculations are based on slightly stronger assumptions.
        - Can we make that assumption? that would be
    - In 2014, "[[Nash Equilbria for Quadratic Voting]]" shows that the difference from the ideal is O(1/N) without strong assumptions.
        - but since [[Bayesian equilibrium]] is used for this proof, it is not explained here.
        - Rough commentary here conveys the atmosphere.

Why quadratic costs are good
- ![image](https://gyazo.com/78edad99698c1844d5808c5a95d3339e/thumb/1000)
- Consider a two-option vote to choose A or B.
- 1 person 1 vote ([[one vote per person]]) voting mechanism where the voter votes +1 or -1 ($v_i \in \{-1, +1\}$)
    - If the sum of them $\sum_i v_i$ is greater than 0, A wins
- But different people have different "how strongly they want that outcome" $u_i$.
    - Voters can only vote +1 or -1 ($v_i \in \{-1, +1\}$)
    - As a result, "Being A is very important!" ($u_i = +10$) and "I don't care either way, but if I had to choose, I'd say B..." ($u_i = -1$) votes have the same power and cancel out
    - This is not good!
        - If there is another person with the same preference as person #2, the [[one vote per person]] voting mechanism would decide on B
            - In that case, each person's utility is (-10, +1, +1)
        - If we had chosen A, it would have been (+10, -1, -1), so this one has a larger sum of everyone's utilities.
            - The one-person, one-vote voting mechanism would select options that would cost the minority a great deal of money.
                    - [[tyranny of the majority]] by [[Alexis de Tocqueville]].
                    - [[When they first attacked the communists]] by [[Martein Niemöller]].
        - Sum of everyone's utility: $\sum_i u_i$ to be determined by
- So we'll let the voters express "how strongly they want that outcome" $u_i$.
    - But if you ask a simple question, "How strong is strong enough?" the higher the number, the higher the probability of getting the result you want, so you end up with [[one vote per person]] in effect, with everyone claiming the maximum strength
    - So we require payment of a cost $c(v_i)$ for increasing the "strength".
    - How to design this cost function $c$ to be "good" is the topic of this paper
- First, we need to define "goodness."
    - robustly optimal:
        - $\sum v_i$ and $\sum u_i$ have the same sign
    - That is, the results of the decision when the number of votes are added together and the results of the decision when the "strength of feeling" are added together.
- Assume everyone agrees with the marginal pivotality $p$ proposed by Mueller (1973) and Laine (1977)
    - Probability of changing the outcome of one vote.
    - This assumption is a pretty strong assumption
- The rational number of votes in this case would be the one that maximizes [$ 2u_i pv_i - c (v_i)
    - The 2 is absorbed by the coefficient part of c, so it doesn't matter, but the resulting utility of A is $+u_i$ and the utility of B is $-u_i$, so it doubles
    - p is "pivotality per vote", so $pv_i$ is the pivotality, and multiplying by $u_i$ gives the expected utility
    - Individual maximizes expected utility minus cost
- Robustly optimal if and only if c is a quadratic function
    - The proof is developed in a separate paper and briefly summarized in the text.
    - simply put
        - Since $2u_i pv_i - c (v_i)$ is maximized, differentiating by $v$ gives 0
        - $2pu_i = c(v_i)'$ holds.
        - It is convenient for $u_i \propto v_i$ (proportional) to be robustly optimal
        - That only happens when $c$ is a quadratic function.
- By the way, what would a naive "$1.00 per vote" look like?
    - The person with the highest utility buys enough votes to determine the outcome.
    - Auction as a commodity transaction, dictatorship as a decision-making process
- <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>Q: I wonder if "[[move one's heart]]" (actions that elicit empathy and increase the number of friends) is for conventional democracy.
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>A: No. Even with Quadratic Voting, it costs 100 for one person to cast 10 votes, but if you add 10 friends and 10 people each cast one vote, you get 10 votes for 10 costs. There is an incentive to get more people to understand.
- <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>Q. Even if the cost is squared, won't it be like Elon Musk buying it all up?
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>A. It only costs you a square of the cost to buy it outright. If Elon Musk wants to do it and is willing to pay that much, it is preferable.
        - Supplementary explanation: the respondent interpreted "buyout" as "one person becomes a majority"; there is no limit to the number of votes, so the equivalent of a buyout of a product does not occur.
        - If each vote costs 100 yen, and 10,000 people vote, and everyone but the mask votes for A, the mask can decide for B alone by paying 10 billion yen to buy 10,000 votes and vote for B.
        - If people don't like the idea of settling on B, they can pay another 100 yen and vote for A. If people don't like the idea of settling on B, they can pay another 100 yen and vote for A. If people pay 200 yen, the mask needs to pay 20 billion yen.
        - If people do not see the value of paying an additional 100 yen, then the subject is not that important to them and they can decide on B. A or B is worth less than 100 yen. Therefore, it is right that the decision to choose "B" is made at the discretion of Mask. It prevents the "tyranny of the majority" in which the "strongly interested minority" is dragged down by the "uninterested majority.
        - The 10 billion yen paid by Mask at this time adds 1 million yen per person to the national treasury, a large enough price to pay for giving in a decision that is not worth more than about 100 yen.
        - <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>Q. If an individual wants to do it even at the cost of buying up all the goods, does that mean that it is the right thing to do from a social perspective?
        - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>A. The argument of Quadratic Voting is that it is better to respect the will of a person who wants it that strongly, if that person wants it that strongly, than to crush the will of a minority with 99% of the majority. The definition of goodness is robustly optimal: "the result of a decision when the number of votes is added together and the result of a decision when the strength of feeling is added together."
- <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>It doesn't feel democratic unless there is an assumption that there is no bias in cost allocation, something like that.
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>If money is used, the weight of a dollar can vary from person to person. Spending money is not a requirement for QV, so if you think that is a problem, you can democratically distribute tokens that are not money. There are many examples of people doing so in practice, so let's look at some applications.

Applications of Quadratic Voting<img src='https://scrapbox.io/api/pages/nishio-en/pplx/icon' alt='pplx.icon' height="19.5"/>
- Political Decision Making (2019)
    - The QV was conducted in April 2019 as an experiment by the Democratic Executive Committee of the Colorado House of Representatives. Lawmakers used it to determine their legislative priorities for the next two years, choosing from 107 bills... . provided by [[Democracy Earth]], an open-source [[liquid democracy]] platform for promoting government transparency. --- [Quadratic voting - Wikipedia](https://en.wikipedia.org/wiki/Quadratic_voting)
- President's Cup Hackathon Voting (2019): in Taiwan, QV was applied at the President's Cup Hackathon event organized by [[RadicalxChange]] in Taipei.
- Public budget allocation: The Taiwanese government's e-democracy platform "[[Join]]" uses QV to promote citizen participation in budget matters.
- etc...
- The situation is roughly "about 5 years after it was first used".

Arrow's impossibility theorem
- <img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>Arrow's impossibility theorem is the theory that in the context of collective decision-making, it is impossible for any given voting rule to satisfy all of the several axioms it is thought to satisfy (e.g., non-dogmatic, Pareto efficiency, independence, etc.). This means that traditional voting systems are limited in their ability to fairly and efficiently reflect complex social preferences; Quadratic Voting offers one solution to this problem.
- <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>A voting system of good nature is impossible!
- ↑upThis is incorrect [[overgeneralization]].
- What the public imagines by the word "voting" is not what Arrow is dealing with here.
- Arrow's impossibility theorem states that "no preference voting system can simultaneously satisfy the conditions for ~."
    - What is a preference vote?
    - <img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>Preference voting ([[preference voting]], [[ranked voting]]) is a voting method in which voters express their own [[preference order]] for multiple choices in an election or decision. In this method, the voter ranks all the options in order of preference, beginning with the most preferred option. Preference voting often yields more informative election results because it can reflect relative preferences among alternatives in greater detail.
- Previously [[Majority Judgement Study Group]], we talked about how Majority Judgement is not subject to the impossibility theorem because it votes on "absolute ratings" rather than on the "preference order" of the alternatives
- This time, Quadratic Voting is a similar system (at least in its original conception), in which people vote on the "absolute rating" rather than the "order of preference" of the choices.

Continued Value
- Reason for the reservation "at least in the original conception."
- > As is common in the analysis of markets for private goods (Willig, 1976), we assume there are enough issues and that each is sufficiently inconsequential that every voter has a quasi-linear “continuation value” for retaining voice credits for future votes.
    - <img src='https://scrapbox.io/api/pages/nishio-en/GPT-4/icon' alt='GPT-4.icon' height="19.5"/>As is common in market analysis of private goods (Willig, 1976), assume that there are enough issues, each sufficiently irrelevant, that every voter has a "[[Continued Value]]" that holds a say credit for future votes.
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>In today's general voting, voting credits are "tokens that lose value if not exercised at the time", but "[[Speaking Credits]]" in this paper can be "saved" for a future vote.
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I know some QVs use a continuation value and some don't.
- <img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>Yes, when using Quadratic Voting (secondary voting), there are systems that use continuation value (carryover) and those that do not.
    - When using continuity value, participants can carry over voting rights (or their value) not used within a certain period of time to the next period. This allows participants to use resource-saving strategies if they wish to have a greater impact on future votes.
    - In a system that does not use continuity value, on the other hand, each voting period is independent and unused voting rights are lost. This is a simple and direct approach, but gives participants an incentive to strategize only within each voting period.
- For example, in the Taiwan President's Cup Hackathon voting, 99 voting credits are given out to voters.
    - You can try these types of ballots at [RxC QV](https://quadraticvote.radicalxchange.org/) right away.
- This method is easy, but the feeling of "it would be a waste if I don't use up the 99 votes I received" causes people to vote even for things they don't value very much.
    - (worth continuing) [[QV is a meaningful mechanism for not voting]].
- On the other hand, if you can carry over credit, you can say, "I don't have a good voting target, so I'll save it.
    - This is closer to a true statement of voter preference strength.
    - But it's hard to implement because it requires ongoing account management and so on.

Quadratic Funding
- > [[Liberal Radicalism: A Flexible Design For Philanthropic Matching Funds]]
- > Buterin, [[Vitalik]] and Hitzig, Zoë and Weyl, Eric Glen (2018)
- > (abst)We propose a philanthropic/public design against funding. This will ensure that a decentralized, self-organizing public goods ecosystem is (nearly) optimally provided. This concept extends the idea of QV to a funding mechanism for endogenous community building. Citizens donate money to projects that are of value to them. The amount of money a project receives is proportional to the square of the sum of the square roots of the donations received. In this "standard model," this yields optimal public good provision. Transformation can limit costs, help protect against collusion, and assist coordination. We will discuss its application to campaign finance, the open source software ecosystem, news media funding, and urban public projects. More broadly, we will relate our mechanism to political theory and discuss how a solution to this public goods problem could provide neutral, non-autocratic rules for society and yet support collective organization.
- In short, you QV in currency.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- Instead of implementing the continuing value of voice credits as a system, leave it to the currency, which is the "continuing value credits" that already exist.

Gitcoin
- <img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>As an application of Quadratic Funding (QF), [[Gitcoin]] is of particular interest.
    - Gitcoin uses QF to fund open source projects and other public goods. QF is a mechanism whereby when there are many small donations to a project, they are amplified using matching funds. This allows projects that are supported by a larger number of people to receive more funds and encourages investment in projects that are of high value to the community The QF is a fundraising tool for projects that are not only supported by the public but also by the community.
    - For example, Gitcoin Grants, in the ninth round of funding for blockchain projects, over 12,000 contributors donated a total of $1.38 million to 812 different projects. The platform determines the amount of matching funds a project receives based on the number of people who have made small donations. This method increases the opportunity for small or emerging projects to raise funds without having to rely on large donations.
- Overall, we have distributed more than 50 million USD, which is more than 7.5 billion yen in Japanese Yen.
- I searched for "OSS donation" to get a sense of scale, and a familiar company was at the top of the list.
    - [Recommendation of donation to OSS ~ Cybozu's donation strategy to OSS - Cybozu Inside Out | Cybozu Engineer's Blog](https://blog.cybozu.io/entry/2022/06/17/150207)
        - > The total amount of donations is currently set at 0.05% of sales. As to why sales rather than profit, we based it on sales rather than profit because we are still using OSS regardless of whether we are making a profit or not.
    - [Cybozu's "kintone" Sales Surpass 10 Billion Yen--Medium to Long-Term Investment Going Forward - Cloud Watch [https://cloud.watch.impress.co.jp/docs/news/1481021.](https://cloud.watch.impress.co.jp/docs/news/1481021.) html]
        - > Consolidated sales for 2022 will increase 19.4% y/y to 22.067 billion yen.
        - Appropriate because I had trouble finding out what recent data was available to the public.
    - Gitcoin is redistributing roughly 700 Cybozu companies.
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>QV/QF is definitely an important part of the attempt to solve social problems through technology.

Plural Management Protocol
- Previously: [[Plural Management Study Session]].
- > Introduces Plural Management, a model that partially replaces hierarchical organizational authority with a plural mechanism that enables networked authority. Participants gain influence by predicting and achieving organizational priorities and use this influence to set priorities and validate contributions, thereby fostering a dynamic, merit-based power structure. This approach, illustrated by the example of open source software development, emphasizes valuable contributions and diligence without the need for hierarchical bottlenecks, thereby strengthening participation and enabling adaptive collective knowledge.
- > Key words: management, plurality, secondary mechanisms, open source, software management, organizational dynamics
- ![image](https://gyazo.com/f1adcb67a3ac4116d16d0425c7ebd729/thumb/1000)
- > Organization members can dynamically earn management credits through their work. Issue boards allow members to prioritize assignments through [[Quadratic Funding]] using credits. These credits are paid to members who contribute to these issues. Payments are made only after a second vote taken by other members who consume management credits to exercise their authority.
- >  Organizational managers may choose to allow members to earn management credit by correctly predicting voting results, rewarding individuals for due diligence in their contributions, or predicting the preferences of existing managers.
- >  This protocol allows for dynamic administrative control through a mechanism that scales from a small group of members to a large organization with no simplified hierarchy.
- Previous exchange
    - > <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>I wonder why they squared it. This is an item that could be tuned in a variety of ways.
    - > <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/> That's [[Quadratic Voting]].
    - > <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>You have a mathematical basis!
- This is explained in this issue.

[[Gov4Git]]
- Gov4git implementation of [Plural Management Protocol
- That's how [[Pluralitybook]] is managed.
    - [https://github.com/pluralitybook/plurality](https://github.com/pluralitybook/plurality)
    - > GlenWeyl: this should be a show and tell
- The last time we did the [[Plural Management Study Session]] on 1/26, we were in a situation where we hadn't received any credit yet.
- As of 3/14
    - ![image](https://gyazo.com/95fbbf520e911fbe17bfc8eb9082966e/thumb/1000)![image](https://gyazo.com/f4151b037a85c47fbd64622a3382f950/thumb/1000)
    - [Gov4Git community dashboard · Issue #263 · pluralitybook/plurality](https://github.com/pluralitybook/plurality/issues/263)
        - You can see detailed data here.
        - ![image](https://gyazo.com/29332ba1f6dc173fa8d028a85a83e44f/thumb/1000)
- What was the experience like at this point in time?
- It's a little interesting to look at the issues prioritized by credits and see what you might be able to contribute.
    - I sense that they're motivated by incentives and induced to do things that are good for the community.
        - Compared to this situation, I feel that the move of "doing the implementation you want to do without reading the community's issues and then suddenly making a Pull Request" is "an act of an individual trying to consume the limited public good "review energy"".
        - There is a sense that OSS projects are taking a step in the direction of using mechanisms to avoid falling into the [[Tragedy of Common Land]].
- The contribution itself was verifiable on Github alone, but how the contribution was valued by the community was unverifiable, a value in the mind of each individual, and now it is visualized as credits.
    - ![image](https://gyazo.com/839a476c8d02d070eb97787dfaa21805/thumb/1000)
        - Overly detailed
        - Maybe this is what Github can show compactly now.
            - ![image](https://gyazo.com/af8b72f00f15905925e69421643e08d6/thumb/1000)
- Currently, I feel we are still in the tutorial state of the game, the main story has not started.
    - Issues built by ordinary participants like me are not Gov4Git managed.
        - ![image](https://gyazo.com/265aff1817b1e1051ef2f641002b016c/thumb/1000)
        - I can't get a gov4git tag, I don't have the authority to put it on, maybe Glen does.
        - It is correct that [[benevolent dictator.]] governs in the early stages of an OSS project
    - I believe Glen also makes the decision on whether to accept pull requests.
        - The PMP paper talked about the community using the prediction market to make decisions, but that hasn't been done yet.
        - Frankly, I think the current phase of trying to do a manuscript FIX on 3/17 is the best time to get Pull Requests, so I don't think the community needs to make a decision if it's going around here alone.
    - Issue of Credit
        - ![image](https://gyazo.com/f53f4833228a3ae4bc0a0b7a64e24d0d/thumb/1000)
        - There are very few Transfers and they are Issue.
        - concrete example
        - [Issuing credits to Nishio · Issue #407 · pluralitybook/plurality](https://github.com/pluralitybook/plurality/issues/407)
        - ![image](https://gyazo.com/1fa07a34d20d8b86fc69689a5cddd048/thumb/1000)
        - Glen has issued me a credit of 160,000, which is a nice chunk of change.
        - I believe this is issuing credits directly through the admin command, not through QF distribution.
    - So, I have yet to experience most of the features described in the paper.
        - Now that I've been recognized for my contribution and have a vote, I'm in a position to observe the stage not from the audience but as a performer.
        - I'm wondering how the difference between the software and the nature of the project, which is a book, will affect the project.

summary<img src='https://scrapbox.io/api/pages/nishio-en/Claude/icon' alt='Claude.icon' height="19.5"/>
- ![image](https://gyazo.com/ae1acdb372c8ed350fb9d8d539433d4d/thumb/1000)
- The last study session provided an overview of Plural Management, a protocol that combines the desirable characteristics of a hierarchical organizational structure and a flat, decentralized organization, dynamically assigning management authority based on individual contributions and management decisions It aims to.
- This workshop delved deeply into Quadratic Voting and Quadratic Funding, which are at the core of Plural Management. system designed to allow participants to express the "strength of their opinions" through their votes. Unlike the traditional one-person, one-vote system, which fails to reflect the strength of an individual's preferences, Quadratic Voting makes it possible to reflect the strength of preferences in voting by making stronger arguments more costly.
- We also gained a better understanding of the mathematical basis for Quadratic Voting. By making the cost function of voting a quadratic function, the sum of the voting results and the "strength of feeling" will match. This is expected to improve fairness and efficiency in collective decision-making.
- Quadratic Funding is an application of the idea of Quadratic Voting to the funding of public goods, where Quadratic Funding is practiced on platforms such as Gitcoin to promote investment in projects of high value to the community. Quadratic Funding is being implemented on platforms such as Gitcoin to promote investment in projects of high value to the community.
- Combining the previous discussion of Plural Management with this understanding of Quadratic Voting and Quadratic Funding, the structure of Plural Management has become clearer. A dynamic, meritocratic power structure is formed when members of an organization earn management credits and use them to participate in prioritizing tasks and evaluating contributions.
- Plural Management is still a developing concept, but it has the potential to solve problems with conventional organizational structures and enable organizational management that is more adaptive and utilizes collective knowledge. We felt that further research is needed on the issues involved in implementing Plural Management in actual organizations and how to adjust the system in the future.
- I thought it was OK as is as a summary without any reworking.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

question
- <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>Q. I'm starting to feel that we should have, for example, "200 - age" as a voting right.
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>A. That is one approach to improvement from the viewpoint of Japanese youth who want to reduce the voice of the elderly because they have too much power, but there is the idea that a system in which the number of votes is influenced by the attribute of age causes a division between those who lose and those who gain. Voting has the advantage of being able to change the weight of votes according to one's interests, without causing a division based on attributes.
- <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>Q. Is the QV independent of the talk about things like the death vote not decreasing?
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>A. In Quadratic Funding, every vote contributes to "how much will be distributed," so there are no "dead votes" that are not reflected in decision-making. However, if you think so, you can carry over your vote without voting, so "I voted, but it has zero value" will not happen.
- <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>Q. When does a voter feel that QV is better than regular voting? Q. When does a voter feel that QV is better than regular voting?
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>A. The ability to express the strength of your opinion and to vote for more than one option is an advantage. The ability to carry over votes when you are not interested in the voting subject is also an advantage, but this is only if the tokens have a continuing value. The 99-vote mechanism of the Taiwan Presidential Cup Hackathon is more of an interesting UI device than a good Quadratic Voting.
- <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>Q. Does QV only let you vote in whole numbers?
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>A. Those restrictions are not in the QV itself. We are just doing that in the Taiwan President's Cup Hackathon.
- <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>Q. Why not provide a separate incentive to vote for more than one (e.g., give an additional cost allocation)?
    - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>A. It would be good to experiment with various UX designs like that.

- <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>Q: Can we take the strategy of dividing and increasing to many the number of agendas on which a person is likely to vote high cost in order to destroy the utility of a person's vote?
    - A: If there is someone who can control the agenda, and that person can set the agenda to the detriment of certain people, then such an attack can be established. In this case, Audrey Tang argues that we should "[[open up agenda-setting authority to people]]" because the abuse of "the power to control the agenda" is the problem.

- <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/> A very good example of [[token economy]].

Discussion of "Voting Coupons"
- <img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>In this conversation we are talking about the idea of "voting coupons" as an incentive to participate in the voting process. These coupons would be earned by participating in the voting process and could be used at the next voting opportunity. In addition, a suggestion has been made that if there is more than one vote, the coupon could be increased on the spot. There is also discussion about a mechanism whereby coupons would be returned if the option that one supported is not adopted, so that all participants would have some degree of satisfaction.
    - Voting coupon suggestion: Voters who participate in the polls receive a coupon that can be redeemed at the next voting opportunity. This would be an incentive to participate in voting.
    - Coupon Increases: In the case of multiple voting, coupons could be increased immediately upon voting. This serves as a mechanism to encourage more active participation.
    - Coupon return: Coupons are returned if the supported option is not adopted. This idea is proposed as a way to reduce dead votes (i.e., votes that do not influence the outcome because they are too few) and to provide a certain level of satisfaction to all participants.
- The purpose of this system is to provide a fairer feeling to participants and to motivate them to participate in the voting process.
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Commenting from a QV perspective.
- <img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>Consider the proposed idea from a Quadratic Voting (QV) perspective.
    - Introduce voting coupons: A system whereby people receive voting coupons for participating in the polls is an interesting mechanism for encouraging participation; in the context of QV, these coupons would represent a "strength of voice" that could be used in future polls. In other words, by participating more, you increase your right to have a stronger voice in the future. This approach has the potential to encourage long-term participation and greater involvement in the voting system for participants.
    - Coupons that can be used at the next voting opportunity: The restriction that coupons can only be used at the next voting opportunity provides an incentive for participants to remain involved in the voting process on a regular basis. This may encourage continued participation and strengthen the base of active participants in the community decision-making process.
    - Increased Coupons from Multiple Voting: Within the QV framework, increasing coupons by voting for multiple options gives voters an incentive to consider a variety of opinions and vote for a broader agenda. This is expected to avoid excessive concentration of votes on a single agenda or candidate and encourage more balanced decision-making.
    - Returning coupons if preferences are not met: In QV, the cost of voting is proportional to the square of the number of votes cast for a choice, but a system that returns voting coupons if preferences are not met reduces dead votes and reassures participants that it is acceptable to take risks. This encourages participants to actively express their views and may contribute to a more fair and inclusive decision-making process.

unused fragment
- Corporate Governance (2014): Posner, E. A., & Weyl, E. G. (2014). Quadratic voting as efficient corporate governance. the University of Chicago Law Review, 81(1), 251-272. [PDF [https://chicagounbound.uchicago.](https://chicagounbound.uchicago.) edu/cgi/viewcontent.cgi?article=1642&context=law_and_economics]
    - Proposal to be used to determine shareholder voting rights


---
This page is auto-translated from [/nishio/Quadratic VotingとPlural Management勉強会](https://scrapbox.io/nishio/Quadratic VotingとPlural Management勉強会) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
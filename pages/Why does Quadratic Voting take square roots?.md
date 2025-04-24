---
title: "Why does Quadratic Voting take square roots?"
---

2023-07-13
Why does [[Quadratic Voting]] take square roots?
- On the common question, "Why take square roots?"
- [Quadratic Voting: How Mechanism Design Can Radicalize Democracy [https://www.researchgate.net/publication/325310987_Quadratic_Voting_How_](https://www.researchgate.net/publication/325310987_Quadratic_Voting_How_) Mechanism_Design_Can_Radicalize_Democracy], with some additional explanations


![image](https://gyazo.com/78edad99698c1844d5808c5a95d3339e/thumb/1000)
- In an existing two-option vote to choose A or B, voters can only vote +1 or -1 ($v_i \in \{-1, +1\}$)
    - If the sum of them $\sum_i v_i$ is greater than 0, A wins
- But different people have different "how strongly they want that outcome" $u_i$.
    - Voters can only vote +1 or -1 ($v_i \in \{-1, +1\}$)
    - As a result, "Being A is very important!" ($u_i = +10$) and "I don't care either way, but if I had to choose, I'd say B..." ($u_i = -1$) votes have the same power and cancel out
    - Not good!
- So we'll have them express "how strongly they want that outcome" $u_i$.
    - But if you ask a simple question, "How strong is strong enough?" the higher the number, the higher the probability of getting the result you want, so everyone claims the maximum strength, which is in effect [one vote per person
    - So we require payment of a cost $c(v_i)$ for increasing the "strength".
    - How to design this cost "better" is the topic of this paper
- First, we need to define "goodness."
    - robustly optimal: $\sum v_i$ and $\sum u_i$ have the same sign
    - In other words, the results of the decision when the number of votes is added together and the results of the decision when the "strength of feeling" is taken into account and added together.
- Assume that everyone agrees with the marginal pivotality of votes $p$ proposed by Mueller (1973) and Laine (1977)
    - Probability of changing the outcome of one vote.
    - I think this assumption is a pretty strong assumption.
    - Maybe you have to put it in to get the solution.
- The rational number of votes in this case would be the one that maximizes [$ 2u_i pv_i - c (v_i)
    - It doesn't say why this is happening.
        - (so it must be in another paper on marginal pivotality)
        - Postscript:.
            - 2 doesn't matter because it is absorbed by the c part, and the result is that A's utility is $+u_i$ and B's utility is $-u_i$, so it doubles
            - p is "pivotality per vote", so $pv_i$ is the pivotality, and multiplying by $u_i$ gives the expected utility
    - [Slide](https://galton.uchicago.edu/~lalley/Talks/Purdue.pdf), using [[Nash equilibrium]] to illustrate.
    - Broken link, the paper is this (since the authors' names are the same): [Nash Equilbria for Quadratic Voting](https://arxiv.org/abs/1409.0264)
- With these assumptions, we can prove that c is robustly optimal if and only if it is a quadratic function
    - The proof is developed in a separate paper and briefly summarized in the text.
    - simply put
        - $2u_i pv_i - c (v_i)$ is maximized, so if we differentiate by v, we get 0
        - $2pu_i = c(v_i)'$ holds.
        - It is convenient for $u_i \propto v_i$ (proportional) to be robustly optimal
        - That only happens when $c$ is a quadratic function.

concrete example
- Suppose there are three voters and the strength of feeling is +2, -1, -1
- If each person votes for one, the negative wins with two negative votes.
- In the case of QV, we think the vote will be proportional to the strength of feeling and will balance out at plus or minus zero.
    - At this time, the plus person has a cost payment of 4
        - Seems somewhat counter-intuitive.
        - (People tend to equate "strength of feeling" with "amount paid.")
- In the case of fixed costs, such as one vote per dollar (i.e., when the number of votes is proportional to the cost)
    - The positive side feels that one vote has greater utility than the negative side.
    - Both votes are the same price, so in cases where the negative side buys a vote, the positive side also buys one.
    - This ensures that the negative side will not win if everyone behaves rationally, and the negative side agents smart enough to foresee this will not buy meaningless votes.
    - The plus side buys the smallest unit of votes and becomes a "dictatorship by those who feel most strongly about it".

Supplemental information on how to pay costs
- There are at least two major implementations of how to pay the costs
- 1: Pay for it
    - Route leading to [Quadratic Funding
    - See [[Gitcoin]] and other examples here.
- 2: Give participants, say, 99 votes, and then vote on it.
        - [[Taiwan President's Cup Hackathon]], etc.
    - This is the equivalent of "distributing a fixed amount of non-transferable virtual currency that disappears at the time of the voting deadline and making people pay with it.
    - Numbers such as 99 have no intrinsic meaning; they simply have a different appearance because "voting by real number value" is difficult for most voters to understand.
    - By the fact that the currency can only be used for voting, there is no incentive to leave it behind, so all participants use up the given amount, and unlike 1, everyone's consumption cost is equal.
    - This method reads "cost c(v)" as "vote" instead of "vote v", so it is expressed as "taking the square root".
- Originally, this paper was envisioned as 1.
- On the other hand, the feature of "making voters pay real money" made it difficult to apply in the real world, and 2 was born.
- Since 1 was later called Quadratic Funding, there are more cases where the term "Quadratic Voting" is used to refer to 2.

### image ver.1
 2023-07-13
![image](https://gyazo.com/0f90b66770c30114403a2b5dde11b0d9/thumb/1000)

---
This page is auto-translated from [/nishio/Quadratic Votingはなぜ平方根を取るのか](https://scrapbox.io/nishio/Quadratic Votingはなぜ平方根を取るのか) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Nash Equilbria for Quadratic Voting"
---

from  [[Quadratic Voting and Plural Management Study Group]]
Nash Equilbria for Quadratic Voting
[Nash Equilbria for Quadratic Voting](https://arxiv.org/abs/1409.0264)
2014
(Summary translation) A voter making a binary decision purchases votes from a centralized clearinghouse and pays a price equal to the square of the number of votes purchased. The net profit of an agent who purchases v votes with utility u is $Ψ(S_{n+1})u-v^2$. where Ψ is a monotonic function taking values between -1 and +1 and $S_{n+1}$ is the sum of all votes purchased by the n+1 voters participating in the election. Let the voter's utility arise by random sampling from a probability distribution $F_U$ with compact support. Each voter knows his own utility, but not the utilities of other voters, but the sampling distribution $F_U$. The Nash equilibrium of this game is described. These results suggest that the expected inefficiency of any Nash equilibrium decreases as 1/n

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>[[Compact support]] refers to the property in mathematics that a function takes on nonzero values only in a finite interval and zero in the rest of its range.
- Assuming that no one would pay 10 billion yen to cast 10,000 votes when the first vote is 100 yen.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>A brief explanation of the process.
<img src='https://scrapbox.io/api/pages/nishio-en/Claude/icon' alt='Claude.icon' height="19.5"/>This paper is a theoretical analysis of the efficiency of the [[quadratic voting]] (QV) mechanism in the [[collective decision-making problem]] of binary choice.
The main flow of the paper is as follows

- The model setup for the QV mechanism is described. Each voter purchases votes based on the strength of his or her preference, and a decision is made based on the total number of votes cast.
- We show the existence of Nash equilibrium and discuss the basic properties of voter behavior in equilibrium.
- The average preference of the voter population is 0, indicating that the inefficiency at equilibrium converges to 0 under sufficiently large population sizes.
- If the average preference of the voter population is non-zero, the total number of votes in equilibrium is concentrated at a constant value, indicating that the inefficiency converges to zero. However, discontinuity points can arise in equilibrium.
- For equilibrium analysis, elaborate applications of probability inequalities and central limit theorems for sums of random variables in independent same-distributions.
- It does not present numerical examples from simulations, but focuses on proving theoretical asymptotic efficiency.

As described above, this paper theoretically analyzes the nature of the Nash equilibrium under a large population for the QV mechanism and proves its asymptotic efficiency.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>How can we say that Nash equilibrium exists?
<img src='https://scrapbox.io/api/pages/nishio-en/Claude/icon' alt='Claude.icon' height="19.5"/>The paper argues that the existence of Nash equilibrium can be said for two reasons.

### 1. Theorem 4.5 of Reny (2011) can be applied
.
Reny (2011) presents an existence theorem for Nash equilibria in Bayesian games. The existence of Nash equilibria is guaranteed by verifying that the conditions of this theorem are satisfied by the QV model in this paper.

Specifically, we confirm that the following conditions are met
- Expected gains conditional on each voter type (strength of preference) are continuous
- Best response according to type is monotonous and satisfies supermodularity

### 2. Monotonicity of optimal response response
.
It shows that the optimal response response of voters (which types vote and how much) is monotonically increasing with respect to type. This means that voters with stronger preferences (higher type values) buy more votes.

This monotonicity follows from the fact that the voter's expected gain is supermodular with respect to type and number of votes purchased.

These two points indicate that Nash equilibrium exists in the QV model treated in this paper. However, it is also noted that uniqueness of equilibrium does not hold in general.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>What is the average preference of the voter population?
<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>In this paper, it is assumed that the type (type), which represents the strength of each voter's preference, is represented by a real number u, which is distributed according to a probability distribution function F. The mean preference µ is defined as the expected value of the type under this probability distribution.

`μ = E[u] = ∫ u dF(u)`

If μ = 0, it means that the voting population as a whole is neutral toward both options.

One of the main results of this paper is that the properties of the Nash equilibrium differ significantly depending on the value of the mean preference μ. In particular, it is shown that the continuity and asymptotic efficiency results of the equilibrium change qualitatively when μ = 0 and when μ ≠ 0.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>What is inefficiency in equilibrium?
<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>Inefficiency in equilibrium is the degree to which the outcome of collective decision making does not maximize the sum of the utilities of all voters in the Nash equilibrium under the QV mechanism. In this paper, we define expected inefficiency (EI) as a measure of inefficiency.
(... Formula omitted<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>)EI is the utility of the entire voting population under the realized collective decision, normalized by twice the maximum possible utility and taking the difference from 1/2.
When EI = 0, it means that the equilibrium under the QV mechanism is perfectly efficient (maximizing the utility of all voters). On the other hand, when EI > 0, it indicates that inefficiency exists.

The main result of this paper is that under a sufficiently large voter population, EI converges to 0 when the number of voters N → ∞. In other words, the QV mechanism is shown to be asymptotically efficient.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
> If the average preference of the voter population is non-zero, the total number of votes in equilibrium is concentrated at a constant value, indicating that inefficiency converges to zero.
For what reason?

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>
It has been shown that if the average preference μ of the voter population is non-zero, the total number of votes in equilibrium is concentrated at a constant value and inefficiency converges to zero. This is due to the following reasons.

### Concentration of total number of votes
.
It has been shown that under a sufficiently large voter population, the total number of votes V in equilibrium converges with probability to a constant value ξ (... Formula omitted <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>)
Intuitively, this concentration is due to the fact that voters with strong preferences (extremists) strategically refrain from voting. If extremists cast a large number of votes, the total number of votes cast would fluctuate greatly. Thus, extremists have an incentive to refrain from voting and to keep the total number of votes within a certain range.

### Convergence of inefficiencies
.
The fact that the total number of votes is concentrated in ξ shows that the collective decision outcome Ψ(V) converges to Ψ(ξ) with probability 1.
Also, since under a sufficiently large population, the sum U of the preferences of the entire voting population approaches μN,
`E[UΨ(V)] ≈ μN Ψ(ξ) ≈ 2E[|U|]`
is valid. This means that the inefficiency measure EI converges to 0.

As shown above, when mean preference μ ≠ 0, the strategic behavior of extremists keeps the total number of votes at a constant value, resulting in more efficient collective decision making.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
> Intuitively, this concentration is due to highly preference-driven voters (extremists) strategically withholding their votes. If extremists cast a large number of votes, the total number of votes cast would fluctuate significantly. Thus, extremists have an incentive to refrain from voting and keep the total number of votes within a certain range.
I don't understand here.

<img src='https://scrapbox.io/api/pages/nishio-en/Claude/icon' alt='Claude.icon' height="19.5"/>...
If extremists buy a large number of votes, the total number of votes V will vary widely. This means that the collective decision rule Ψ(V) will change discontinuously.

For example, if the total number of votes changes from positive to negative, Ψ(V) will jump discontinuously from +1 to -1. At this time, extremists increase the likelihood that their preferred option will not be realized.

Extremists then have an incentive to moderate their own vote counts, anticipating that other extremists will buy a large number of votes. In other words, extremists are strategically restraining each other's vote counts.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
> If extremists buy a large number of votes, the total number of votes V will vary widely. This means that the collective decision rule Ψ(V) will change discontinuously.
I don't understand here.

<img src='https://scrapbox.io/api/pages/nishio-en/Claude/icon' alt='Claude.icon' height="19.5"/>....

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I suspect that EXTREMISTS who are not expected to reach the conclusion they prefer will buy lots of votes.

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>You are right. You are right that EXTREMISTS who are not expected to reach their preferred conclusion have an incentive to buy lots of votes.

In fact, the model in this paper shows that when the mean preference μ is not zero, a discontinuity point can arise as extremists purchase large numbers of votes (Theorem 3).

Specifically, under a sufficiently large voter population, almost all voters will be "moderate" and behave in such a way as to keep the total number of votes near ξ. However, extremists are always present, albeit with probability 0.

The extremists attempt to buy a large number of votes in order to shift the total number of votes from ξ significantly. The result is a discontinuous change in the total number of votes V and the possibility of the collective decision being overturned.

However, the probability of occurrence of such extremists is shown to decrease exponentially as the number of voters N increases. In other words, under a sufficiently large N, the impact of extremists becomes negligibly small.

So overall, the main conclusion of this paper is that the total number of votes is concentrated around ξ, making collective decision making more efficient.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>"The probability of occurrence of extremists decreases exponentially as the number of voters N increases" is shown by which equation?
<img src='https://scrapbox.io/api/pages/nishio-en/Claude/icon' alt='Claude.icon' height="19.5"/>
It is shown in the proof of Theorem 3 that the probability of occurrence of extremists decreases exponentially as the number of voters N increases.
Specifically, in the proof, it is shown that the number of extremists Ne satisfies the following probability inequality (Equation (57))
P{Ne ≥ k} ≤ (α^k / k!) · (1/n^(k/2)) for all k ≥ 1
where α is a constant that depends on the preference distribution.
This inequality implies that the probability of Ne being greater than k decreases exponentially as N increases.

See the paper (p. 32)<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
![image](https://gyazo.com/fef84a9d9b3306bfddcad3d1f35a28e1/thumb/1000)

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>(continued)
In particular, consider the case k=1,
P{Ne ≥ 1} ≤ α / √n
This is the case. That is, the probability that there is more than one EXTREMIST is decreasing on the order of O(1/√n).

I see.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- I questioned him because the intuitive explanation he gave was not intuitively correct to me, but if the players who vote in large numbers converge to zero, then I'm convinced.
- This is a typical rebuttal to the QV: "Won't the rich buy lots of votes?" It's also a rebuttal to the typical backlash against QV: "Don't rich people buy a lot of votes?

---
This page is auto-translated from [/nishio/Nash Equilbria for Quadratic Voting](https://scrapbox.io/nishio/Nash Equilbria for Quadratic Voting) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
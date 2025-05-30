---
title: "Mechanism Design (Book)"
---

![image](https://gyazo.com/b3945c4e4d3b89b02283d87bb8e80629/thumb/1000)
    - [[mechanism design]] - [[resource allocation]] design of the system and [[incentive]]
    - [[Toyotaka Sakai]] ,  [[Yuji Fujinaka]] ,  [[Takuma Wakayama]]  (2008)
- [Amazon](https://amzn.to/3bh0WLN)

> The 2007 Nobel Prize in Economics was awarded to Leonid Hurwitz, Eric Maskin, and Roger Myerson for "fundamental contributions to mechanism design theory.
- [[Maskin's theorem]]

- [[Definition of Strategic Resistance]]

- Correspondence with [[theory of games]] (→<correspondence source concept>)
- Each individual $i \in I$ has a set of messages $\mathscr{D}_i$ (→ preference space)
- Each individual strategically chooses a message $\succsim_i \in \mathscr{D}_i$(→preference)
- The function $f$ that gives the consequence determines the consequence of the game [$ f(\succsim)\in X
- Counter-strategy is the [[ruling strategic equilibrium]] of the true preference group itself in this game.
    - [[direct game]] : $(\succsim, \mathscr{D}, f)$
    - [[direct mechanism]] : $(\mathscr{D}, f)$

No distinction is made between the ideal to be realized ([[social choice function]]) and the method used to guide it ([[direct mechanism]]).
- I would like to distinguish this
- Also, [[ruling strategy equilibrium]] is a kind of [[open concept]], but it is difficult to handle, so I would like to extend it to handle general solution concepts.

Set of messages $M_i$
Pair of messages $m \equiv (m_1, m_2, \ldots, m_n) \in M_I \equiv M_1 \times M_2 \times \cdots \times M_n$
Function to choose a consequent for a pair of messages (consequent function) $g: M_I \to X$.
$M \equiv (M_i)_{i\in I}$
Mechanism (indirect mechanism): $(M, g)$ #Definition of mechanism
Direct mechanism: $M_i = \mathscr{D}_i, g = f$
Game $(\succsim, M, q)] for true preference pair [$ \succsim \in \mathscr{D}_I$
Mechanisms are generators that give games to each true preference.
mechanism
Think of the corresponding S that is as [[open concept]] of the game
- $S(\cdot, M,g) : \mathscr{D}_I \twoheadrightarrow M_I$

$g(S(\succsim, M, g)) \equiv \{x \in X : \exists m\in S(\succsim, M, g), x = g(m) \} = F(\succsim)$
![image](https://gyazo.com/fef969317b35be72e7755f6858d42463/thumb/1000)
![image](https://gyazo.com/e9e1076b3684c08b04ec2921669890b3/thumb/1000)


- [[non-repudiability]]
- If Gian, with the help of Dekisugi's suggestion, says, "Let's all share Suneo's New Year's money equally!" Nobita has no reason to oppose it.
- Suneo can't refuse to object alone.
- [[Bayesian incentive compatibility]]


Table of Contents
Chapter 1 [[SOCIAL CHOICE]] and its execution
- 1.1 Introduction
        - [[King Solomon's dilemma]]
            - [[Glaser-Marmanism]]
- 1.2 Basic Concepts
    - 1.2.1 [[Social Choice Response]] and Execution Mechanism
    - 1.2.2 Concept of Mechanism Design
- 1.3 [[Nash Execution]] and [[Maskin's theorem]]
    - 1.3.1 Definitions
    - 1.3.2 Maskin's theorem
    - 1.3.3 Criticisms of the Maskin Mechanism and Nash Execution
    - 1.3.4 General Feasibility and Individual Mechanism Design
- 1.4  [[strategicity]]
    - 1.4.1 [[Domination Strategy Execution]] and Strategy Resistance
    - 1.4.2 [[Non-domination strategy implementation]] and strategy resistance
    - 1.4.3 [[Nash Execution]] and Coalition Tolerance

Chapter 2 [[public decision-making]].
- 2.1 Introduction
- 2.2 Voting Environment
    - 2.2.1  [[Gibert-Saththwaite theorem]]
    - 2.2.2 Domain Expansion
    - 2.2.3 Domain Reduction
- 2.3 Probabilistic environment
    - 2.3.1 Substantial Execution
    - 2.3.2  [[system of random dictatorship]]
- 2.4 Quasi-linear environment
    - 2.4.1 Configuration
    - 2.4.2  [[Groves function]]
    - 2.4.3  [[expected externality function]]

II Application
Chapter 3 [[exchange economy]].
- 3.1 Introduction
- 3.2 Basic Settings
- 3.3 Operation of [[Walras Distribution]] and [[Hurwitz theorem]]
    - 3.3.1 Strategic Manipulation in an Exchange Economy
    - 3.3.2 Generalization of the Hurwitz Theorem
    - 3.3.3 Related Matters
- 3.4 Nash Execution
    - 3.4.1 Walras Distribution and [[Constraint Walras Distribution]]
    - 3.4.2 Execution Mechanisms for Constraint Warlas Response

Chapter 4 Auction
- 4.1 Introduction
- 4.2 Basic Settings
- 4.3 Auction rules, strategies, and their synthesis
    - 4.3.1 Auction Rules
    - 4.3.2 Strategies
    - 4.3.3 Synthesis of Auction Rules and Strategies
- 4.4 Auction Objectives
- 4.5 Efficient Auction
    - 4.5.1  [[Second Price Auction]]    [[second-price auction]]
    - 4.5.2 First Price Auction
- 4.6 [[income equivalence theorem]] and [[Optimal Auction]]
    - 4.6.1 Setup
    - 4.6.2 Income equivalence theorem
    - 4.6.3 Optimal Auction

Chapter 5 [[fair share]].
- 5.1 Introduction
- 5.2 Basic Settings
    - 5.2.1 Model
    - 5.2.2 Nature and Axioms of Resource Allocation
- 5.3 Strategic Resistance
    - 5.3.1 Impossibility Theorem
    - 5.3.2 Possibility theorem
- 5.4 Nash Execution Potential

Chapter 6 [[non-dividend goods exchange]].
- 6.1 Introduction
- 6.2 Basic Settings
- 6.3  [[Top Trading Cycle Algorithm]]
- 6.4 Executability of Strong Core [[Core (Game Theory)]].
- 6.5 Application to renal transplant matching

Chapter 7 [[matching]].
- 7.1 Introduction
- 7.2 Basic Settings
- 7.3  [[Gale-Chapleau algorithm]]
- 7.4 One-sided dominance strategy
- 7.5 Bilateral Domination Strategies
- 7.6 Maskin Monotonic Response
- 7.7 Basic Settings for Many-to-One Matching
- 7.8 Treatment of ≿b in many-to-one matching and basic results
    - 7.8.1 ≿b as an order derived from extended preferences
    - 7.8.2 ≿b as a priority
- 7.9 Boston Method


---
This page is auto-translated from [/nishio/メカニズムデザイン(書籍)](https://scrapbox.io/nishio/メカニズムデザイン(書籍)) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
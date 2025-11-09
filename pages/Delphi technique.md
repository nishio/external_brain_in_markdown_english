---
title: "Delphi technique"
---

<img src='https://scrapbox.io/api/pages/nishio-en/GPT5/icon' alt='GPT5.icon' height="19.5"/>
Compact 👇 the main points of the Delphi Method (Delphi Method)

Yes?
A method of collegiality in which opinions are collected anonymously and iteratively from experts (or parties involved), with statistical summaries and feedback returned in each round, and finally convergence/agreement or clarification of issues; originated in RAND in the 1950s. Designed to avoid the negative effects of face-to-face meetings (peer pressure, disparities in voice).

Basic Flow
1. panel selection: ensure diversity of disciplines and positions (N=15-50 is typical)
2. Round 1 (exploration): Extract issues and hypotheses through open-ended questions and broad questions
3. summary: categorize and consolidate responses (frequency, typical reasons, scatter)
- Round 2 (Evaluation): Evaluation of Round 1 proposals in terms of importance/relevance, etc. (Likert, ranking) + re-consideration
5. feedback: median and interquartile range, ratio of approval/ disapproval and reasons for representation of the opposing side
6. Round 3+ (Convergence): Re-perform evaluation (optional description of reason for change). Terminate with stopping criteria (IQR≤1, rank stable, change <5%, etc.)
7. finalization: report consensus items/conflict items/uncertain areas

forte
- Anonymity and repetition reduce peer pressure and increase the quality of reasons
- Extract systematic knowledge from geographically dispersed experts
- **Quantitative (statistics) x Qualitative (reasons)** can be obtained at the same time.

limit
- Depends on panel configuration (selection bias)
- Round design is difficult (granularity and number of questions)
- Convergence does not = correct answer / Possibility to degrade creativity of minority opinions

variation
- Classic Delphi: Consensus-oriented
- Policy Delphi: dares to visualize the range of issues and reasons for the dispute (more of an issue than an agreement)
- Real-time/online Delphi: constant answers + feedback as needed for short-term convergence

Practical design points
- Anonymity: individual votes are not disclosed, only the aggregate is shared
- Quality of feedback: median + IQR + reasons for representation (both for and against)
- Preliminary agreement on criteria for suspension
- Preservation of minority opinion: leave the report with a concomitant statement of the reasons for not agreeing
- Number of rounds: 2-3 rounds is realistic (1-2 weeks/round is a good rule of thumb)

Indicator example (per Round)
- Median / Interquartile range (IQR)
- Stability of Spearman correlation of ranks
- Percentage change in opinion after reassessment (%)
- Percentage of new codes appearing in free descriptions (%)

Question Template (for use only)
- R1 (Search)
    - Please list the three most important issues on this topic and give reasons why."
    - Two viable solutions plus prerequisites/side-effects."
- R2 (evaluation)
    - 'Rate each solution on a scale of 1-7 for effectiveness, feasibility, and timeline. One word of rationale."
- R3 (Convergence)
    - 'I would maintain/change the rating after looking at the median/IQR and say a few words about why.'

Standard Report Structure
- Consensus (IQR Sub) items and recommended actions
2. issue clusters and the main rationale for each position
3. area of uncertainty (additional research required)
4. insight into minority opinions (prevention of oversight)

Differences from Jigsaw-type AI dialogue (roughly)
- Delphi: Expert/parties' iterative evaluation → agreement/debate
- Jigsaw article method: individual in-depth + collective reflection + representative statement generation (representativeness evaluation)
→ Close in purpose, but Delphi has statistical indicators and anonymous iterations at its core, while Jigsaw strengthens the participation experience and public data nature.

Recipe for AI Application (for your context)
- Summary and cluster: R1 free description → theme classification (HDBSCAN, etc.) → representative sentence generation (AI)
- Anti-bias: "Always extract reasons for disagreement" and "Explicitly state unknowns/uncertainties" in prompts
- Automatic indicators: median/IQR and rank stability automatically calculated
- Visualization: opinion map (bubble = frequency, color = median rating, border = IQR)
- Audit log: questions, summary, and model settings for each round can be saved/published

Minimum Execution Set (MVP)
- Number of participants: 20-30, 3 rounds
- Tools: Form (R1) → Dashboard (summary) → Evaluation Form (R2/R3)
- Criteria for stopping: IQR≤1 or rank change <0.1 and occurrence of new issues <5%.
If necessary, we can prepare a complete set of questions, aggregation schema (JSON), and visualization mockups for your "in-house AI utilization workshop" or "public hearing AI".


---
This page is auto-translated from [/nishio/デルファイ法](https://scrapbox.io/nishio/デルファイ法) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
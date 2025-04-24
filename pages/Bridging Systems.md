---
title: "Bridging Systems"
---

[[Bridging Systems: Open Problems for Countering Destructive Divisiveness across Ranking, Recommenders, and Governance]]
[[Aviv Ovadya]], [[Luke Thorburn]]
<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
The following is a compact summary of the contents of [[Ovadya & Thorburn (2023)]]'s paper "Bridging Systems: Open Problems for Countering Destructive Divisiveness across Rankings, Recommenders, and Governance" by [[Ovadya & Thorburn (2023)]].

--

# summary of thesis

Increasing social divisiveness (divisiveness) has raised concerns about political violence and increased difficulty in cooperation. Although social collaboration is essential for addressing large-scale issues such as climate change, existing "engagement-first" rankings on social networking services may be fueling divisiveness. This paper proposes a system design that promotes "bridging" - fostering mutual understanding and trust while preserving conflicts and differences of opinion - and proposes the following ### 3 areas
 (1) (1) SNS recommendation systems, (2) large-scale collective response systems, and (3) mini-publics (deliberative assemblies) with face-to-face facilitation.

--

# main points

1. purpose of ### [[Bridging]]
    - The goal is not to homogenize differences or eliminate conflict, but to foster mutual understanding and trust in order to foster "[[constructive conflict]] ([[productive conflict]]).

2.### [[Attention Allocation]] point of view
.
    - Social networking sites, search engines, and facilitators are "allocating" what and how much attention to whom from the vast amount of information. Traditionally, engagement metrics such as clicks and likes have tended to be the most important, but they can be redesigned to include "bridging" factors as well.
    - This is the place.[[Kiite World]]が[[ランキング]]を廃して[[ロングテールなアテンション]]をつくり出しているのと関連している<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

3.### Elements supporting Bridging
.
    - Data and Model (Relation Model).
        - The relationship between users and their statements are represented in graphs and embedded spaces to estimate "which groups are far apart" and "who prefers what kind of content".
    - Signals.
        - Indicators of actions and postings that may mitigate fragmentation. Examples include "[[diverse approval]] (posts with support from a wide range of positions)" and "avoidance of bimodal response patterns.
    - Metrics.
        - A measure of the extent to which the system as a whole is "functioning in the direction of mitigating fragmentation". Utilizes polarization index and surveys (e.g., emotional thermometer).

4.### Open Research Proposals
.
    - What signals and metrics are reasonable, especially universality across cultural differences?
        - Address side effects of optimization for "bridging" (e.g., collection of shallow content, risk of unintended manipulation).
    - Institutional design and governance methods for the actual implementation of bridging (who determines the criteria and to what extent interference is justified).

--

# Conclusion
.

The paper emphasizes the importance of a new research and implementation area called "Bridging Systems" that respects diverse opinions while overcoming fragmentation, as opposed to the fragmentation risk posed by existing "engagement maximization". Specifically, the paper presents avenues for incorporating elements that "promote mutual understanding and trust" in any attention-allocation system, such as social networking recommendation algorithms and deliberative processes, and indicates numerous open problems.

This is the brief abstract of this paper. The paper not only proposes a bridging method, but also presents implementation and evaluation methods and ethical issues to consider, and proposes a multifaceted approach to mitigating fragmentation in society.

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
In systematically implementing and evaluating bridging, the following three main elements are important. The paper organizes these as "Relation Model," "Signals," and "Metrics.

--

# 1. Relation Model
.

## 1.1 Overview
.
- What it does: A model that defines how differences in opinions, preferences, and positions among people are expressed and understood.
- Examples: networks among users on social networking sites, similarity of survey responses, voting and approval/rejection data, etc.

## 1.2 Approach
.
- Graph-based.
- Users are treated as nodes, and connections and interactions between users (followings, replies, etc.) are treated as edges. The weights of edges represent "affinity," similarity, and conflict.
    - [[Proof of Human]]での[[SybilRank]]的なアプローチだね<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- Embedded space-based (multidimensional space)
- The "what kind of topics/worldviews users prefer" is converted into a numerical vector and placed in space, and the degree of similarity and grouping are determined by distance and proximity. There are examples ([[YourView]], [[Polis]], etc.) that compress multidimensional vectors into two dimensions using principal component analysis, etc., and visualize the clustering of people.

## 1.3 Significance
.
- Visualize the fragmentation situation: know what groups are where and how far apart they are.
- Linkage to Signals/Indicators: Use this model to quantitatively estimate which posts and opinions are "supported by different positions", etc.

--

# 2. Signals
.

## 2.1 Overview
.
- [[What it does]]: A "topical" numerical indicator of how much an individual post or comment is likely to contribute to bridging (mutual understanding and trust building).
- Usage Aspects: Considered as a signal other than engagement when ranking content in social networking recommendation algorithms. In particular, "can it contribute to bridging?" is predicted and included in the ranking score.

## 2.2 Concrete Examples
.
1.### Diverse Approval
.
    - The idea is that "content that has a certain amount of support from both groups with different positions is more likely to help alleviate divisiveness."
        - Example: Twitter's Community Notes (formerly [[Birdwatch]]) officially displays only notes that have received "helpful" ratings from users with different views.

2.### Response Bimodality
.
    - The idea is that content that divides responses into two extremes (a U-shaped distribution) may deepen fragmentation, while that which does not may contribute to bridging.
        - An approach has been proposed that actually uses machine learning to detect polarization and reduce the priority of highly polarized items.
        - I'm torn as to whether it's better not to show this or to show it.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

3.### Exposure Diversity (exposure to diverse sources of information)
.
    - We hope to bring in diverse perspectives by "increasing exposure to submissions from different perspectives" and bridging the gap between the two.
        - However, research has pointed to cases of "counterproductive" effects (e.g., deepening antipathy toward the opposing camp), and caution must be exercised in introducing simple

4.### content-based signals
.
    - The linguistic characteristics of posts and comments are analyzed using natural language processing and other methods to determine whether the content is "dehumanizing" or contains derogatory expressions.
        - There are also attempts to detect text patterns that indicate constructive replies or "positive feedback to the other party," for example.

--

# 3. Metrics
.

## 3.1 Overview
.
- What it does: A macro indicator to assess whether the behavior of the system as a whole "mitigates fragmentation and promotes mutual understanding.
- Utilization phase: A/B testing and monitoring to measure whether system changes have helped improve bridging.

## 3.2 Type
1.### Relation Metrics
.
    - Relation Model (graphs and embedding) quantifies the "psychological and opinion distance" between groups.
        - Examples: homophily, modularity, random walk controversy, and other indicators of how fragmented the network is.

2.### Bridging Metrics
.
    - The Relation Model is updated over time and the difference before and after ("has the division narrowed?") is measured.
        - Example: "How did the survey's emotional thermometer (emotional score toward the opposing partisan group) change before and after viewing the post?

3.### Signal aggregation
.
    - A method that uses an increase/decrease in the overall number of signals (e.g., diverse support) as an indicator.
        - Example: if the number of submissions with "diverse support" increases from week to week, we will consider bridging progress.

## 3.3 Notes
- [Validity: It is important to verify that the indicators truly represent "mutual understanding and trust. Formal quantification is meaningless if it does not affect actual relationships.
- reproducibility: The results should be similar under the same conditions and not easily affected by updates in measurement methods or external factors.

--

# Summary
.

- Relation Model
- A model that serves as a basis for visualizing divisions and differences of opinion. Uses graph structure and multidimensional embedding to capture where and what kind of divides exist.
- Signals
- A local indicator of the degree to which individual posts and statements contribute to bridging. Incorporating this as a criterion other than engagement when ranking increases the likelihood that "bridging posts rather than posts that incite division" will be ranked higher.
- Metrics
- Indicators to measure the effectiveness of system modification and to get a "holistic view" to continuously brush up the system. Network indicators and survey results are used to determine whether fragmentation has been alleviated.

By designing and operating these three elements in a consistent manner, the paper argues that "attention allocation" processes such as social networking and discussion systems can be guided in a direction that promotes mutual understanding and collaboration, rather than merely inciting conflict among people.


---
This page is auto-translated from [/nishio/Bridging Systems](https://scrapbox.io/nishio/Bridging Systems) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
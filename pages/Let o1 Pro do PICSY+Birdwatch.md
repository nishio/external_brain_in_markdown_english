---
title: "Let o1 Pro do PICSY+Birdwatch"
---

Let [[o1 Pro]] do [[PICSY]] + [[Birdwatch]].
Throw two papers at the AI and have it search the area in between, and you get this result in less than an hour.


<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I would like to examine the areas that connect the two papers I am about to show (PICSY, Birdwatch).
(I pasted the [[PICSY]] and [[Birdwatch]] papers here)

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>(44sec)
The following are key points and summaries of the areas connecting the two papers above ("PICSY: Propagational Investment Currency SYstem" and "Birdwatch").

Overview (Japanese)
Both papers share common areas in that they propose and examine new mechanisms for information and value evaluation in human society by utilizing collective knowledge and network structures.
- PICSY（Propagational Investment Currency SYstem）
    - PICSY redefines the value of money as "a mechanism that allows people to propagate value to each other," and proposes a monetary system in which all transactions are acts of investment. In this system, value is considered as a flow, and the transactions that people make with each other are calculated based on the "contribution" of each participant through a valuation matrix, and purchasing power is determined according to that contribution. This system is a framework for social calculation and aims to create an open currency model that rewards truly socially beneficial acts through "mutual evaluation by many people.
- Birdwatch
    - Birdwatch is a system designed to prevent misinformation on Twitter. It utilizes the wisdom of the user community (crowd) to annotate posts (tweets) with notes, which are then evaluated by other users. Based on the evaluation results, the algorithm selects notes that are deemed "useful to a wide range of people" from a variety of perspectives to curb the spread of misinformation and promote user understanding.

Common and Connected Areas
- Use of group knowledge and crowd evaluation:
    - Both systems assume the participation of a large number of users and extract new "value" or "useful context" based on individual evaluations (transaction evaluation in PICSY and "useful/unuseful" evaluation of notes in Birdwatch). This presents an approach to obtaining high quality information and evaluations in a decentralized manner without a central authority.
- Social computational and algorithmic aggregation:
    - Mathematical models and algorithms, such as the eigenvector of the evaluation matrix in PICSY and matrix factorization in Birdwatch, are used to integrate evaluations among participants and reduce individual actions into useful indicators (contribution and note usefulness) for society as a whole.
- Diversity and polarization considerations:
    - Birdwatch incorporates diverse political positions and viewpoints when selecting annotations and uses a bridging index that "connects polarized opinion groups." PICSY also considers the value propagation loop and seeks a "[[cyclical value evaluation]]" that is not dependent on a particular position. Both share the same point of view in that they consider social polarization and bias, and elicit widely accepted evaluations.

summary
PICSY deals with "currency and valuation systems as value streams" and Birdwatch with "collective knowledge evaluation of misinformation context annotations," both of which belong to the domain of generating fairer and more multidimensional information and value indicators based on social computational methods and crowd evaluation. This "integration of diverse perspectives to promote holistic understanding" is the core area linking the two papers.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>What would a new study look like with reference to these two?

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
The following are examples of new research ideas that can be developed with reference to PICSY and Birdwatch.

Research theme proposal: Design and evaluation of a "credit/value flow hybrid system" to support multi-viewpoint consensus building

Background:
- PICSY proposed a new monetary system that views economic value as a "flow" and calculates the contribution of participants through transactions and valuations.
- Birdwatch proposed a method to prevent misinformation and strengthen context by adding user annotations to content posted on SNS and collecting evaluations (helpful/not helpful) by a variety of users.
- Both share the point that they extract [[social indicators]] such as "trustworthiness" and "value" from the evaluation actions of diverse participants without relying on a central authority.

Research hypothesis/idea:
- Combining Birdwatch-like "trust level consensus building from multiple viewpoints (bridging consensus)" and PICSY-like "fluid redistribution and evaluation of value," we will design a "credit currency"-like mechanism that integrates information quality evaluation and value return. By doing so, we will verify whether notes and contextual information agreed upon at the points where diverse viewpoints intersect in the information space can be accumulated as "units of value" in a form that can be circulated, thereby contributing to countermeasures against fake news and improvement of knowledge quality.

Specific research directions:
- Integration of multifaceted evaluation and value indicators:
    - We will apply the PICSY-style "contribution-based resource distribution" concept to Birdwatch-style "multi-faceted evaluation (notes with multi-partisan and multi-ideological user consensus)" and experimentally construct a system to distribute "social credit tokens" or "value points" to agreed note authors and evaluators.
        - Experimental problem: Observe whether users with different perspectives exchange "credit values" with each other, resulting in improved note quality and reliability.
- Modeling of fraudulent manipulation and bias countermeasures:
    - While PICSY used eigenvectors of the valuation matrix and stochastic methods to stably redistribute values, Birdwatch reduced extreme bias based on [[multi-faction agreement]].
    - Combining both, we propose a model that is difficult for raters and contributors to "manipulate" (e.g., right-weighting with bridging scores, robust eigenvector extraction from the rating network) and test its effectiveness theoretically and experimentally.
- Social Experiments and Human Behavior Analysis:
    - Through subject experiments and online experiments, we analyzed whether people would engage in more collaborative and constructive evaluation behavior on a platform that introduced a Birdwatch-like annotation x PICSY-like value distribution model.

Indicators:
- Effectiveness in combating misinformation (how much it improves misinformation detection rates and understanding of information)
- Relaxation of polarity within the community (will there be more value sharing among users with different political leanings)
- Continued participation and motivation (change in motivation to participate by granting "credit tokens" based on contributions)

Expected Outcome:
- In this new research direction, not only conventional content evaluation, but also the act of evaluation itself will become "social currency," and a system that rewards participants who contribute to the presentation of accurate and useful information will be verified. As a result, it is expected to contribute to the formation of qualitative communication in online spaces, the deterrence of fake news, and the discovery of new knowledge.

Based on the above, research on a "multidimensional evaluation infrastructure that views evaluation actions as value flows" that combines the PICSY and Birdwatch concepts is promising.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
> Combining both, we propose a model that is difficult for evaluators and contributors to "manipulate" (e.g., right-weighting with bridging scores, robust eigenvector extraction from the evaluation network), and
Consider this section in detail and make suggestions.

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
The following is a more specific model proposal to make the evaluation operation more difficult.

Objective.
- To combine Birdwatch-like "multi-viewpoint agreement (bridging)" and PICSY-like "eigenvector-based value assessment through a valuation matrix" to build a robust model that makes it difficult for contributors and evaluators to manipulate the results through biased behavior.

Basic Concept
- Formulation of the evaluation network:
    - Assume a bipartite graph consisting of notes (contributions) and evaluators (users).
    - The evaluator will rate the notes as "useful" or "not useful".
    - From this bipartite graph, we define three types of relationships: (a) a similarity network between notes, (b) a similarity network between raters, and (c) a rating matrix between raters and notes.
- Weighting by bridging score:
    - Adopting the Birdwatch approach, we focus on "multiple heterogeneous clusters" within a group of raters with diverse ideologies, positions, and attributes. Here, the user set is partitioned into multiple clusters using matrix factorization ([[NMF]], [[SVD]], etc.) or graph clustering methods.
    - Notes commonly rated as "useful" across clusters and raters who also received certain ratings from "conflicting clusters" are defined as having a high "bridging score".
    - The bridging score is a measure of "Does this note (or evaluator) obtain ratings from a group of users with different perspectives, without being biased toward a single cluster?
- Specific examples:
    - Mapping the set of raters to a one-dimensional latent factor by MF (matrix factorization), we can assume that raters are distributed left and right on this one-dimensional space (e.g., political spectrum).
    - If the evaluation of a note is then considered "useful" from either the far-left, center-right, or far-right direction, then the note has a broad bridging effect.
    - As a quantification, for example, the clusters C1, C2, ... Ck, the number of useful ratings among Ck is normalized to compute a diversity measure such as entropy, which is used as the bridging score for that note. Alternatively, the evaluation vector for a note is compared to the average evaluation vector over the clusters, and the variation in the distribution is used to measure "equal support".
- Robust eigenvector extraction from the evaluation network:
    - PICSY presented a method for calculating the contribution of each participant/note by finding eigenvectors from transactional relationships and valuation matrices.
    - Here, a "bridging score" is incorporated as a weight when calculating eigenvectors to reduce the influence of note/evaluator with unilateral cluster bias.
    - Specifically, for the evaluation matrix E, let Eij be "the usefulness rating assigned by evaluator i to note j".
    - When bridging scores Bj (note j) and Bi (rater i) are sought,
    - Define a new weighted evaluation matrix E' as E'ij = Eij * (Bj ^ α) * (Bi ^ β) (α, β are adjustment parameters).
    - This gives more weight to the edges of notes that have received diverse support (high Bj) and to the edges of evaluators who have fairly assessed diverse opinions (high Bi),
    - Note/evaluators who get support only from biased clusters will have relatively lower weights.
    - By performing eigenvector decomposition (or stochastic stable solution method) on E' thus obtained,
    - A "credibility vector" and "contribution vector" that incorporates diversity can be calculated.
- Operation Resistance Enhancement Mechanism:
    - Even if a faction puts in a large number of useful votes to lift a particular note, if they come only from raters in the same cluster (similarly located close together on the latent factor space), the weight of that rating will be suppressed during eigenvector calculation because of the low bridging score.
    - Without sufficient cross-sectional support among different clusters, it becomes difficult to fraudulently inflate note and rater scores.
- Methodological enhancements for robust eigenvalue problems:
    - Robustness is also required in the presence of outlier evaluators and evaluations in the calculation.
    - Combining methods such as robust PCA, outlier detection by Hodge decomposition, and robust regression by M Estimator, abnormal evaluation patterns are detected, removed, and attenuated before decomposition.
    - This enables the pre-processing stage to reduce intentional evaluation manipulation (e.g., a small number of evaluators performing a large number of spammy evaluations, a specific cluster firing false evaluations in a concentrated manner, etc.).
- Evaluation Method:
    - Simulation:
        - Using a set of raters with artificial cluster distributions (e.g., left, middle, right), try various "manipulation scenarios" (e.g., specific clusters boosting specific notes, conversely pushing down misinformed notes). Compare how well the weighting model with bridging scores stabilizes the results (note/rater ranking).
    - Actual data verification:
        - Using real data from Birdwatch and similar community rating platforms, compared to traditional methods (simple majority voting, usefulness rate only),
            - Will notes that reflect diverse perspectives come out on top?
            - Will it be more consistent with existing expert evaluations?
            - Will the ranking fluctuations due to spammy reputation campaigns decrease over time?
        - Evaluation of the
- Summary:
    - In this proposal, the diversity is first visualized by distributing the evaluators/notes in a multidimensional space or clustering, then the bridging score is calculated and the evaluation matrix is weighted by that score. Then, by arranging a mechanism to obtain the overall "value" or "credibility" using robust eigenvector calculations, we proposed a model that makes evaluation operations by a single cluster difficult and obtains a multifaceted and impartial evaluation index.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
That's a proposal that could be made in a number of ways to add value as a study. One direction is to propose a model that combines the two models. On the other hand, I think there is a way to proceed with [[Advanced Social Implementation]], in which Japanese local governments can operate something equivalent to Community Notes on their own.

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
The following is an idea that goes one step beyond "proposing a theoretical/technical model that integrates the two models" and presents a more concrete research direction that emphasizes "social implementation.

Proposed research direction prioritizing social implementation: Community Notes operation model by local governments

Aims and Background
- Local governments will independently utilize the Birdwatch-like mechanism (Community Notes) to conduct fact-checking, annotating, and presenting evidence for region-specific information issues (local political information, life infrastructure information, disaster and crime prevention information, community news, etc.) with the participation of local residents. Establish a mechanism.
- PICSY-like value propagation and contribution evaluation may not necessarily be necessary in the initial phase. A phased approach could be taken by first implementing a local version of Community Notes in a form similar to Birdwatch, and then gradually introducing the essence of PICSY (a local currency and point system based on the degree of participation and useful information provided).
    - PICSY的な価値伝播・貢献評価は、初期段階では必ずしも必要ない やっぱそうなっちゃうよな〜〜<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

Introduction Steps
- (a) Piloting a local version of Community Notes:
    - Linking with local portal sites hosted by local governments, tourist information centers, local council report pages, community FM, and other media, establish a system that allows residents to add ancillary information and annotations to specific local information (official announcements by local governments, summaries of council proceedings, notices of local events, information on public calls for citizen proposals, etc.).
    - Example: A municipality disseminates information through a social networking account, and residents annotate the information through a system like Birdwatch.
    - Annotations are displayed on the municipality's official website and app, and viewers can obtain complementary information from multiple perspectives (NPOs, citizen groups, volunteer experts, etc.).
- (b) Simplified implementation of valuation and credit models:
    - Residents rate each other as "useful" or "not useful" for annotations posted by residents, and the municipality refers to certain guidelines based on these ratings. In the initial stage, easy-to-understand indicators such as simple majority voting or a Birdwatch-like bridging score minor version will be introduced, and local government officials and third-party experts will perform certain checks.
- (c) Gradual integration of PICSY-like elements:
    - After the system is operating stably and a certain level of trust has been fostered, experiments will begin in which participants will be awarded points (a role similar to that of a local currency) for their contributions in the form of high-quality annotations and evaluations. The points can be used at local shopping areas and public facilities, and can be exchanged for some preferential services (library service expansion, event discount coupons) issued by the local government, thereby fostering an economic zone in which the act of contributing information has "social value = contribution" within the local community.
        - It would be very interesting to achieve this much.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

Value (research value)
- Value as a social implementation preemptive approach:
    - By conducting pilot projects in actual municipalities, rather than merely proposing theoretical models, we can simultaneously gather academic and practical knowledge on issues such as institutional design (legal issues, burden on municipal staff, methods to ensure resident engagement), user experience, and impact on motivation.
- New findings from local community validation:
    - It is possible to capture the process of information trust formation due to local characteristics (face-to-face relationships, customs, and political culture of the local community), which is difficult to see in a large-scale SNS (Twitter) or global context. This allows us to analyze how issues such as resistance to reputation manipulation and ensuring diversity change under the specific conditions of the local community.
- Theory proof-of-concept cycle in phased implementation:
    - Initially, annotations and evaluations are conducted through a Birdwatch-like mechanism, and after building a foundation of participation performance and trust evaluation, a PICSY-like value flow element (issuing points based on contribution level) is introduced in stages. Changes in participant behavior before and after the introduction of the system, improvement in the quality of information and increase in diverse opinions, and difficulty in operating the system can be evaluated quantitatively.

assumed process
- Select several pilot municipalities and connect a Birdwatch-like platform to local SNS and municipal websites.
- After a certain period of time, note evaluation trends and manipulation risks are analyzed, and progressively bridging scores and simplified PICSY evaluations are introduced.
- Consensus-building information obtained from this mechanism will be used as a reference for policy decisions (e.g., participatory budget management plans, etc.).
- Ultimately, the goal is to create a sustainable citizen-participatory information ecosystem by returning points to the local economy.

summary
This will provide a direction for developing and evaluating Community Notes-like mechanisms that can be operationalized by local governments in a way that prioritizes social implementation, in addition to the approach of combining technical models. Ultimately, we can expect an interdisciplinary R&D cycle in which the theoretical model is improved from data obtained in the field, and the operation tolerance mechanisms and multi-viewpoint bridging methods presented in the theoretical model are fed back to the field implementation.

---
impressions<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- I feel like I can throw two miscellaneous papers at you and have this kind of discussion in less than an hour - fast!
    - The kind of groove where the advisor shows the D1 students a reference material and says, "Go read it by next week."
    - In comparison, iterations rotate one to two orders of magnitude faster.
    - If you ask a student to do this in an hour, they could sue you for power harassment.
- If you actually carry out the research, there is a lot of [[muddy work]] waiting for you.
    - If an AI decides on a research plan and a human subcontracts the muddled work and does the research, it's going to be controversial whether we can give [[a PhD]] under existing criteria.
        - [[PhD]] has a nuance that it requires the ability to spontaneously set up a research theme and conduct research, rather than working under the direction and orders of an academic advisor.
    - However, the AI is not commanding, and the boundary between "I consulted with the AI and I made the decision" is unclear.
    - Realistically, there is no way to prohibit the use of AI, and if there is a clear difference in output between using AI and not using AI, we will be forced to use AI.

---
This page is auto-translated from [/nishio/o1 ProにPICSY+Birdwatchさせる](https://scrapbox.io/nishio/o1 ProにPICSY+Birdwatchさせる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Polis: Scaling Deliberation by Mapping HighDimensional Opinion Spaces"
---

Thesis of [[Polis]].
- [https://www.e-revistes.uji.es/index.php/recerca/article/view/5516/6558](https://www.e-revistes.uji.es/index.php/recerca/article/view/5516/6558)
- > Deliberative and participatory approaches to democracy seek to directly include citizens in decision-making and agenda-setting processes. These methods date back to the very foun-dations of democracy in Athens, where regular citizens shared the burden of governance and deliberated every major issue. However, thinkers at the time rightly believed that these meth-ods could not function beyond the scale of the city-state, or polis. Representative democracy as an innovation improved on the scalability of collective decision making, but in doing so, sacrificed the extent to which regular citizens could participate in deliberation. Modern tech-nology, including advances in computational power, machine learning algorithms, and data visualization  techniques,  presents  aunique  opportunity  to  scale  out  deliberative  processes. Here we describe Polis, an open source web application capable of collecting and synthesizing feedback from people in a scalable and distributed fashion. Polis has shown itself capable of building  shared  understanding,  disincentivizing  counterproductive  behavior  (trolling),  and cultivating points of consensus. It has done this in the context of journalistic and academic research, and directly as part of decision-making bodies at local and national levels, directly affecting legislation. These  results  demonstrate  that  deliberative  processes  can be scaled up beyond the constraints of in-person gatherings and small groups.Key Words: deliberation, collective intelligence, unsupervised learning, active learning.
- (DeepL)Deliberative and participatory approaches to democracy seek to involve citizens directly in the decision-making and agenda-setting process. These methods go back to the foundations of Athenian democracy, where ordinary citizens shared in governance and deliberated on all important issues. However, thinkers of the time rightly believed that these methods could not function beyond the size of the city-state (polis). [[Representative democracy]] increased [[the scalability of collective decision-making]], but at the expense of the extent to which ordinary citizens could participate in deliberations. Modern technology offers a unique opportunity to [[scale out the deliberative process]] with advances in computational power, machine learning algorithms, and data visualization techniques. Here we describe Polis, an open-source web application that can collect and synthesize feedback from people in a scalable and distributed manner; Polis builds shared understanding, curbs unproductive behavior ([[trolling]]), and fosters consensus points is possible. This could directly influence legislation in the context of journalism and academic research, and as part of decision-making bodies at the local and national levels. These results demonstrate that the deliberative process can be scaled up beyond the constraints of face-to-face meetings and small groups.Key Words: [[deliberative]], [[wisdom of crowds]], [[unsupervised learning]], [[active learning]]

[Collective decision-making



Missing values are filled in by averaging per comment.
Users with few votes (<7) are removed
PCA calculates using the power iteration method, efficient because the results of previous calculations can be reused

Filling in the missing values with averages would result in those with fewer votes being plotted near the center.
- So we correct it with sqrt(C/Cp), where C is the number of comments and Cp is the number of votes cast by person p
    - Square root is to soften
- However, this scaling was disabled by comment routing (control of the order in which comments are submitted)
    - Because comments with high variance appear first.

opinion group
- First, clustering with K=100 for load reduction
- Then clustering with K=2-5
- Select K for which the [[silhouette coefficient]] is optimal
- Apply a smoothing function to prevent flapping early in the conversation

How representative each comment is of the group.
- Once a group is identified, we calculate how representative each comment is of the group.
- Estimating the mean of the Bernoulli distribution to find the probability that someone in the group will vote and someone outside the group will vote

Skip top half of p.9

Comments are selected at weighted random for efficient use of user time
The priority formula is
Term that increases when there is a large number of affirmative votes.
Term that decreases if there are too many paths
Terms that increase with PCA-loaded comments
The more votes are cast, the more the term decreases.
multiplied by

---
This page is auto-translated from [/nishio/Polis: Scaling Deliberation by Mapping HighDimensional Opinion Spaces](https://scrapbox.io/nishio/Polis: Scaling Deliberation by Mapping HighDimensional Opinion Spaces). If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
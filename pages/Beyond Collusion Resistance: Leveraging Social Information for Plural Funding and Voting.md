---
title: "Beyond Collusion Resistance: Leveraging Social Information for Plural Funding and Voting"
---

[[Joel Miller]]
[[E. Glen Weyl]]
[[Leon Erichsen]]
December 2022

[https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4311507](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=4311507)

memo
- [https://chatgpt.com/c/6886143e-b6e0-8329-9a0c-03ca3529ce8f](https://chatgpt.com/c/6886143e-b6e0-8329-9a0c-03ca3529ce8f)
    - [[Would you say that QV is strategic in its resistance?]]

<img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>Aim of the paper
- Traditional Quadratic Funding (QF) assumes "independent rational individuals" and ignores social ties and cooperative behavior.
- In reality, relationships among friends, organizations, communities, etc. strongly influence donation behavior, and [[civil attacks]] and [[collusion]] occur.
- This paper redefines "collusion resistance" and explores design principles for a Plural QF that actively exploits people's social bonds.

- [[Pairwise Discounting]]
    - Reduce subsidies for similar pairs (yellow rectangles)
    - More accounts with more people can earn linear subsidies.
- [[Cluster Match]]
    - Calculate square root per group
        - (1) Linear increase in subsidy if one person belongs to multiple groups
        - (2) Can be abused even among overlapping groups
    - →Squared Cluster Match
- COCM: [[Connection‑Oriented Cluster Match]]
    - Interaction term attenuates donations of "members socially close to the other group" by √c
    - Fully meet defined collusion tolerance
    - →Maintain IR (Individual Reasonableness) for each individual.
- Offset Match
    - Estimate social centrality αᵢ and replace each contribution by √αᵢ cᵢ
    - Linear equations for α may not be solved; there are cases where IR is not satisfied
    - Sufficient condition: All members can belong to a single group as well.
- Eigen Match
    - Cluster Match by considering eigenvectors of social graphs as "pseudo-groups
    - Conceptual phase (untested)
    - Possibility to combine the advantages of Offset and Cluster

Redefining Collusion Resistance (Summary)
- The subsidy for incremental individual donations is limited to O(√cᵢ).
- Subsidies for group-wide donation expansion are also O(√β), where β is the expansion rate.
- The increase in subsidy due to additional members is limited to O(√x), O(√γ) for both the number of new members x and the amount of each member's contribution γ.
The appendix proves that COCM meets these three conditions.

Conclusion/Implication
- Incorporating social information can better reward "consilience across differences" while reducing collusion.
- The COCM and other new mechanisms will be applied not only to the allocation of public funds but also to Quadratic Voting.
- Future issues include (1) robustness evaluation under incomplete or erroneous information, (2) more precise modeling of group structure, and (3) deeper exploration of unverified mechanisms such as Eigen Match.

A word summary
- Re-contextualize QFs to maximize cooperation among diverse communities while preventing collusion. The key is to incorporate "who is closer to whom and how close they are" into the subsidy calculation.


AI Considerations
- Just as ENIAC replaced manual calculations, COCM is the first [[funding allocation algorithm]] to replace "[[the independent individual model]]" and incorporate the [[social graph]] directly into calculations as weights.
- COCM mathematically rewards "[[Cooperation Across Differences]]" with the rule that "the closer the connection, the thinner the subsidy; the farther away, the thicker. This is a mathematical expression of Plurality's philosophy that "diversity is value.
    - While the [[prediction market]] measures opinion strength by the amount bet on one axis, the COCM adjusts subsidies on two axes, √c × social distance, making the economic signal [[polyvocal]].

[[Leon papers]]

---
This page is auto-translated from [/nishio/Beyond Collusion Resistance: Leveraging Social Information for Plural Funding and Voting](https://scrapbox.io/nishio/Beyond Collusion Resistance: Leveraging Social Information for Plural Funding and Voting) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
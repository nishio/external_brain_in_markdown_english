---
title: 'Recapturing the Second Argument "Semantic Argument" on the Truth Thesis'
---

[PDF](https://www2.kansai-u.ac.jp/tetsugak/2024/%E6%A6%8E%E6%9C%AC.pdf)
<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
Summary of key points
- The "[[Semantic Argument]] (SA)" in [[Floridi]] is an attempt to argue for the "[[Truthiness Thesis]] (VT)" that [[semantic information]] ([[semantic information]]) is necessarily true.
- SA first eliminates tautologies (constant-true formulas) and contradiction formulas, and also eliminates inconsistency. Finally, however, it tries to conclude that a proposition cannot be informative unless it is true, based on the fact that "the amount of information is reduced when false propositions are included.
- However, this implicitly leads to the assumption that "false" propositions have "negative information content," an assumption far removed from general information theory. If we keep the usual assumption that "the amount of information is always greater than or equal to 0," then there is no argument to establish VT by eliminating false propositions, and we end up with a "truth-neutral information model that eliminates only inconsistencies.
- The author highlights this contradiction by carefully reconstructing the "distinction between the argument domain (the distinction between the set of propositions D and the set of information S)" and the "interpretation of the information content (probability plus elements of epistemic value including truth and falsehood)," and points out that in Floridi's argument there is a "[[negative information content]]" He points out that a special assumption is latent.
- As a result, although Floridi's SA raises only the conclusion that "semantic information is true," it is in some ways incompatible with general information theory. Furthermore, as a good example of the interplay between information-theoretic quantitative analysis and qualitative analysis, which assigns special epistemic value to "information that is true," this paper provides material for a fresh look at the VT controversy.

Overall Significance
- Although Floridi's SA, which defends the VT (truthfulness thesis), has traditionally been criticized, this paper, in particular, reexamines whether the qualitative approach (admitting only true information?) and the quantitative approach (calculating the amount of information) are compatible without contradiction by uncovering the unexplored issue of the "negative nature of information quantity".
- If "negative information content" is not accepted, SA can only justify the elimination of inconsistency, and remains a "truth-neutral" information model that does not question truth or falsehood. On the other hand, assuming negative information content can indeed eliminate false propositions, but this is very different from ordinary information theory.

In any case, the discussion is useful in reevaluating the core of Floridi's philosophy of information regarding truthfulness.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
I feel like there is a fallacy in this argument of the type that if f(S1+S2)<f(S1) then f(S2)<0 for a function f that takes some set S as an argument, what do you think?

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
Key Points of Responses

As you pointed out, we assume that "some measure (or information quantity) $f$ is simply additive to the sum (or annexation) of sets", and on that basis
$f(S_1 + S_2) < f(S_1) \quad \Longrightarrow \quad f(S_2) < 0$
It is often a fallacy of metric and additivity to lead to the

Essentially, we need to look rigorously at "what conditions make (or prevent) $f(S_1 + S_2) = f(S_1) + f(S_2)$ hold?" Especially in Floridi's argument,
- "Isn't additivity $P2$ limited to the case where the sets of information are independent of each other?"
- "The "reduction in overall information" when adding false or contradictory propositions may not be captured by ordinary (simple additive) measures in the first place."
This is a problem.

In other words, if we assume that the Floridean "information content" is really an "additive measure",
$f(S_1 + S_2) < f(S_1) \quad \Rightarrow \quad f(S_2) < 0$
It is easy to jump to the conclusion that But in fact,
- In phases where additivity breaks down (merging mutually contradictory propositions, including false propositions, etc.), $f(S_1 + S_2) \neq f(S_1) + f(S_2)$ is occurring, and it is a logical leap to ask whether we should regard that as "negative information content",
- Or, it is possible that Floridi is secretly envisioning a special metric (different from the usual non-negative metric) that "destroys" the amount of information when a contradiction or falsehood is introduced.
There are two interpretations.

Therefore, the inference "$f(S_1 + S_2) < f(S_1)] so [$ f(S_2) < 0$" tends to fall into the "metric fallacy" without careful consideration of how far the additivity condition is secured. As pointed out in the paper, Floridi's four principles (non-negativity, additivity, inverse relation principle, and elimination of zero information) are actually ambiguous as to whether they can be applied to all sets, and may fail if the discussion area is not limited.

summary
In conclusion, the short-circuit that "adding false reduces the overall information content → therefore false has a negative information content" is,
- Is the "information content" function really additive at all times?
- How is a measure defined when it contains false or inconsistent
If the law is enacted without clarification of the "what" and "how" of the law, there is a strong suspicion of "fallacy" as you have pointed out.

Floridi's argument, to begin with, assumes properties that are slightly different from those of "general information theory measures," and any form of deriving "negative information content" that leaves that unanswered is seen as a leap in logic that misunderstands the assumptions of the measure.

---
This page is auto-translated from [/nishio/真理性テーゼに関する第二論証「意味論的議論」を捉え直す](https://scrapbox.io/nishio/真理性テーゼに関する第二論証「意味論的議論」を捉え直す) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
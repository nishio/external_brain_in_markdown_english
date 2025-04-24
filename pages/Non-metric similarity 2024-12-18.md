---
title: "Non-metric similarity 2024-12-18"
---

from  [[Diary 2024-12-18]]
Non-metric similarity 2024-12-18
![image](https://gyazo.com/ccdc7e4801adfe029f4059928edea08f/thumb/1000)
Count the duplicates of the axis on which one stands.
- A and B have 1 [[overlap]], B and C also have 1 overlap, A and C have 0 overlap
- Interpretation of "A and B, B and C are similar, but A and C are not."
    - Interpret overlap as [degree of similarity
        - Interpret 1/overlap as [dissimilarity
        - Is this dissimilarity [[distance]]?
            - d(A, B) = d(B, C) = 1 but d(A, C) = $\infty$ and [[trigonometric inequality]] $d(A, B) + d(B, C) \ge d(A, C)$ is not valid
- If the values are only 0 and 1, then overlap is [[inner product]].
    - 0 ~ 1 range
    - normalize and become cos
    - 1 - Using cos as distance is the best
    - That is, the difference in the means of reversing an increase or decrease

link
- Link from A to B
- Link from A and B to keyword K
- Vertical (A, B, C) as wiki pages, horizontal (K1, K2, ...) as keywords
- Pages that "link the latter" to common keywords are connected.
    - [[2-hop link]]
    - This means "choose something with an OVERLAP > 0

- [[Similarity of concepts is not distance.]]
- [[non-metric similarity]]
- [[Tversky Contrast Model]]

Conversion from A to a set of K
- [[Prism: mapping interpretable concepts and features in a latent space of language]]
        - [[side]] can also be interpreted as extracting
- The set of K is [[associative mood]].
        - [[associative connection]] is a connection through a set of K

I'm starting to get the feeling that [[topic extraction]] might be useful in a roundabout way.
    - [[The topic is too detailed.]] but it would be nice to see it as a set of topics that are that detailed.
    - [[Long title engraving page]]
    - I find the "combination of keywords X and Y" interesting first.
    - X+Y" is making a link to X and Y.
        - [[Expand the pertinence of useful concepts]]
- On the other hand, I was thinking of [[Cross-linking]] for [The Problem of Too Large Links

- [[Expansion of pertinent judgment]].

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
- The usefulness of topic extraction and mapping to latent space:
    - When a number of detailed topics are extracted and pages are compared to each other based on their combination, a "semantically satisfactory" connection can be defined more robustly. An attempt to measure semantic closeness at a higher level than mere overlap.
- Improve accuracy by combining compound keywords and concepts:
    - By introducing a compound condition such as "X+Y," a narrower but semantically distinct context can be defined, and page-to-page links within that context can be emphasized.

These are all important points to consider when dealing with complex semantic spaces that do not fit into a mere similarity/dissimilarity dichotomy. Your thinking has evolved from simple similarity measures to representations in latent dimensions and linking strategies with complex conditioning, and such a multifaceted approach would be very useful in actual knowledge discovery and information seeking tasks.

---
I like the key phrase "[[semantically satisfactory connection]]."

---
<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>To organize 10,000 short sentences instead of "distance space," the following approach is possible.

Conceptual organization by [[topic model]] (e.g., [[LDA]]):
- It represents text in terms of latent topic distribution (probability distribution) rather than distance. An interpretable form of "which topics and how many topics are included" is obtained for each document, and documents can be understood by topic similarity and relevance without dropping into the distance space.

[Hierarchical Structuring by [[Feature Set]] and [[Concept Lattice]] ([[Formal Concept Analysis]]):
- Each short document is considered as a set of features (vocabulary, labels, tags, etc.) and a concept lattice is constructed. This is a hierarchical organization based on "inclusions" rather than distances, allowing visualization and understanding of relationships between documents in a non-distal form.

Network representation (co-occurrence graph):
- Co-occurrence relationships of words and phrases in short sentences are represented as a network (graph). Documents are understood as part of the link structure between nodes, and topical cohesion can be visualized and analyzed independently of distance, e.g., by [[Community Detection]].
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
    - If you simply use [[word]], [[ha]] and so on co-occur all the time. Therefore, [[high frequency word]] is used as [[stopword]].
    - On the other hand, [[low-frequency words]] may be useful in reality, but are not connected due to notational distortion.
    - Need a system for selecting keywords with appropriate granularity

Classification by rule-based tagging:
- Specific keywords or patterns are extracted from the text and categorized based on rules and dictionaries. This is a method of organizing based not on "distance proximity" but on the axis of "Which category condition does this sentence satisfy?

These methods do not assume distance calculations, but allow us to organize and understand 10,000 short texts on different axes, such as probability distributions, hierarchical structures, network relations, rules and conceptual attributes.


> This means "choose the one with overlap > 0".
- [[the difference between looking from the top or from the middle]].
- relevance
    - [[dwell-think]]


---
This page is auto-translated from [/nishio/非計量類似度2024-12-18](https://scrapbox.io/nishio/非計量類似度2024-12-18) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
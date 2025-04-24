---
title: "Euclidean distance to general distance"
---

from  [[Blind spot card with no picture yet]]
Euclidean distance to general distance

Doesn't it have to be the Euclidean distance? However, if the distance from the origin is of little value and it is important that the vectors are similar in direction from the origin, it is inconvenient to use the Euclidean distance because the vectors with very different directions around the origin are judged to be close to each other. In such cases, the angle between them is used as the distance (see Cosine Similarity).

Cosine similarity corresponds to normalizing a vector onto a hypersphere of radius 1 and using the length of the arc between them. Such "projection onto another low-dimensional space and use the distance there" is often used. In principal component analysis, plotting and observing on the first and second axes is looking at the distance projected in two dimensions.

Conversely, the support vector machine uses a kernel trick to project to another higher-dimensional space and use the distance there.

The average assumes the existence of addition and scalar doubling, but generalized medians can be used in general distance spaces.

Use of hyperbolic space [https://papers.nips.cc/paper/2029-hyperbolic-self-organizing-maps-for-semantic-navigation.pdf](https://papers.nips.cc/paper/2029-hyperbolic-self-organizing-maps-for-semantic-navigation.pdf)

__BELOW_IS_AI_GENERATED__
# ユークリッド距離を一般の距離に
 2023-09-05 00:42 <img src='https://scrapbox.io/api/pages/nishio-en/omni/icon' alt='omni.icon' height="19.5"/>
### Summary of notes
.
When evaluating vector similarity, it is important to consider not only the Euclidean distance, but also other distances. For example, if the direction is more important than the distance from the origin, it is useful to use the cosine similarity. Projection to lower or higher dimensional spaces is also often used. Even in general distance spaces, averages can be obtained by using generalized medians.

### Relation to Fragment
.
The fragment "Similarity of concepts is not distance" is closely related to the note. The note discusses the choice of distance in evaluating vector similarity, and the fragment questions the treatment of that distance as concept similarity. The fragment "The curse of dimensionality" is also related to the note and points out problems with the evaluation of distances in higher dimensional spaces.

### summary of thoughts
The choice of distance in evaluating vector similarity should depend on the nature of the concept that the vector represents. In addition, evaluating distances in high-dimensional spaces is difficult and requires the selection of appropriate distances.

### title of thought
.
"The choice of distance in vector similarity assessment and the problem in higher dimensional spaces."

### extra info
TITLES: `["Blind Spot Cards Still Without Pictures"], "Concept Similarity Is Not Distance", "Bots to Aid Reading", "Vector Similarity", "The Curse of Dimension", "Stable Diffusion Study Group", "Abstraction and LSH"]`
generated: 2023-09-05 00:42
---
This page is auto-translated from [/nishio/ユークリッド距離を一般の距離に](https://scrapbox.io/nishio/ユークリッド距離を一般の距離に) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
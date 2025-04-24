---
title: "Non-metered MDS"
---

Kruskal, J. B. (1964). Nonmetric multidimensional scaling: a numerical method. Psychometrika, 29(2), 115–129.
[PDF](http://cda.psych.uiuc.edu/psychometrika_highly_cited_articles/kruskal_1964b.pdf)
<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>This paper details the procedures and algorithms for numerically implementing the Nonmetric Multidimensional Scaling Method (Nonmetric MDS) proposed by Kruskal (1964). The main points are as follows.

Purpose: From the non-metric similarity (ordinal information) between given objects, we place points in a low-dimensional space, assuming a monotonic transformation of distances, and evaluate their goodness of fit with a measure called "stress".

Basic Procedure:
- Rank the similarity between the objects and approximate the distance between the points such that they satisfy the similarity ("monotone regression" procedure).
- To minimize stress, the placement is updated using an iterative gradient descent method (steepest descent).

Computational ingenuity:
- Dealing with partially missing data: If there are missing values, stress is defined only on the observable portion.
- Can handle common distance functions such as Minkowski distance.
- Countermeasures to local minima problems include iterations from different initial placements and reasonable stopping criteria (slope magnitude and stress level).

Monotonic regression procedure:
- To perform optimal distance fitting while maintaining similarity ranking, the distance values are adjusted using a block join algorithm.
- This paper provides concrete implementation details (array structure, normalization procedure, step size control, iteration stopping conditions, etc.) and systematically summarizes the then novel computational method, providing a basis for subsequent researchers to easily apply and improve non-metric MDS.

---
This page is auto-translated from [/nishio/非計量MDS](https://scrapbox.io/nishio/非計量MDS) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Merging Distributed Representations"
---

- When there are two [[distributed representations]] A, B
    - Both, normalized (mean 0, variance 1) in each axis direction and concat
    - Then [[dimensional reduction]] in [[PCA]].
- Dare to use linear PCA for dimensionality reduction
    - It does not bend space, so it preserves features related to addition and mixing of distributed representations as pointed out in the work of [[word2vec]].

- Should normalization be done or not?
        - [[Is rotational neglect appropriate?]]
    - In distributed representations created by word2vec training, etc., the rotation information is not important because it is just [[spontaneous symmetry breaking]] due to random initial values.
    - However, when merging human-created distributed expressions, "up", "right", etc. have meaning.
        - Symmetry breaking due to characteristics of human cognition
    - Is linear dimensionality reduction possible based on the assumption that certain axes are adopted?
        - For example, if the two axes you add match the two axes of the other's 200-dimensional variance representation, then of course they will be merged.
        - PCA is the mapping of 202 dimensional data to 200 dimensional data is dimensionality reduction, and PCA is to find the rotation matrix that minimizes the loss
        - In the present case, two more of the 200 dimensions are fixed, so the 198-dimensional subspace
        - The problem is to find the rotation matrix to this subspace

---
This page is auto-translated from [/nishio/分散表現のマージ](https://scrapbox.io/nishio/分散表現のマージ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
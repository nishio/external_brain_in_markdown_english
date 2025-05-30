---
title: 'Regarding "Multiply PCA before k-NN to increase accuracy."'
---

- Dimensionality reduction with PCA before k-NN improves accuracy" → NG
- PCA reduces the number of dimensions, which reduces the time required for calculations.
- More teacher data will improve accuracy" - OK
- If the correlation of the original data is high, dimensionality reduction by PCA is unlikely to reduce the accuracy.
    - If the correlation of the original data is high, dimensionality reduction by PCA will not reduce the accuracy.
    - If the correlation of the original data is high, dimensionality reduction by PCA improves accuracy.
- If the correlation of the original data is high, even if dimensionality reduction is performed by PCA before k-NN, the accuracy is unlikely to decrease, and the time required for calculation will decrease.

- PCA is a rotation, so if you don't reduce the dimensionality, the accuracy of k-NN remains the same" - OK
- When an axis is overfitting due to an overfitting, cutting off that axis will improve generalization performance.
    - The "PCA 'axis with less variance' is the cause of the overfitting" -> The probability of this is not zero, but it is lower than other axes.
    - The axis that is discarded by PCA is "the direction where the variance of x is small after ignoring the label information y in the teacher data entirely," not because it is "less important for identification" or "noise for identification," but simply because "x does not move much in that direction.
- k-NN is greatly affected by the scale of the original data.
    - Normalization improves accuracy" → NG
        - Normalization is "adjusting the variance of each axis so that it is equal to 1," which means "making sure that the axis with the smallest variance is not disadvantaged when all axes are equally important but have different variances due to the sensor's value range or other reasons.
        - PCA is a method of axis rotation that says, "Since axis x1 and axis x2 are highly correlated, the variance of x1 + x2 is large and that of x1 - x2 is small. After rotation, dimensionality reduction is often combined with "Let's ignore the axis with small variance, x1 - x2. It is a rather strange practice to ignore some of the axes with small variance and enlarge the rest.
---
This page is auto-translated from [/nishio/「k-NNの前にPCAを掛けると精度が上がる」について](https://scrapbox.io/nishio/「k-NNの前にPCAを掛けると精度が上がる」について) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
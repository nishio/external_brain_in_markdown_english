---
title: "Phenomenon that Polis with the most votes are lumped together."
---

2024-10-20 [[public opinion map]] Concerns at release

Why? Hypothesis
- Inherently infeasible to represent in two dimensions when multiple topics are mixed together.
    - Then take out a few highly correlated axes?
    - Doesn't happen because the poll map is divided by topic?
    - Wouldn't it be possible to look at the contribution ratio and divide it appropriately?
        - Clustering axes
        - There are N axes, if you take 2 of each, there is no loss of information, but the number of axes will increase, in fact, there must be a combination that does not increase the loss too much
        - Simplify the problem
            - I want to minimize the variance after the 3rd dimension, which is the "lost information" when I do a PCA on each of the N axes in two groups.
            - optimization problem
            - It's going to come down to existing algorithms.
                    - [[Clustering axes]].
- If users can add comments, essentially the dimensionality of the original data becomes higher and higher
    - So you wouldn't be offended by a poll map of fixed questions?
- Problems in handling users who do not respond to all
    - Mathematically possible but not elucidated.
    - As a simple example, suppose there are three opinion groups $(1, 0, 0), (0,1,0), (0,0,1)$.
        - This is an equilateral triangle in two-dimensional space.
        - However, some people don't answer all questions.
            - $(-, 0,0), (1, -, 0), (1, 0, -)$
        - These are by the process of filling in the missing values with the average.
            - $(1/3, 0,0), (1, 1/3, 0), (1, 0, 1/3)$
            - becomes
        - This isn't on the original two-dimensional space.
            - We don't know how bad it will be.
            - In this case, there were three distinct clusters in the first place, but the filling in of missing data with averages generated intermediate data that prevented a clear separation of the clusters.
            - In this particular case, up to one missing case can be restored to its original state if it's filled in with other data.
                - In a situation with a sufficiently large amount of data, it should be possible to recover the data from "other data where the answers are the same" using the k-nearest neighbor method or something like that.
    - Possibly not a good idea to fill in missing values with averages.

But, well, in the meantime, we'll have to work on the Polis math server to solve the problem.

---
This page is auto-translated from [/nishio/投票の多いPolisが一塊になる現象](https://scrapbox.io/nishio/投票の多いPolisが一塊になる現象) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
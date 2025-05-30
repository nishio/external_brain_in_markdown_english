---
title: "How will machine learning be tested?"
---

Q: How do you write software tests for programs that use [[machine learning]]?
A:
- If by "how do we write software tests" you mean how do we guarantee that the behavior is complete, then machine learning cannot do that.

- General software testing assumes that the range and distribution of possible input values are known in advance.
    - The test is to make sure that there is no case that produces strange output within that range.
    - Where the boundaries are clearly verbalized in advance, e.g., in specifications

![image](https://gyazo.com/de5f00b4e0b4aa027c25a60da4ce79c3/thumb/1000)


- Boundaries are not clearly verbalized in machine learning.
    - In some cases, the boundaries are blurred to begin with.
    - Figure with overlap in distribution
    - ![image](https://gyazo.com/85afc26928233cf5ea56cb2cabfe18bb/thumb/1000)
    - Where to draw the boundary when there is overlap
    - If the costs incurred by different types of mistakes vary, the appropriate boundaries will differ even for the same distribution
        - Affected by business requirements
    - We could talk about AUC, but that would be a hassle because we'd have to start with ROC.

- I wrote this diagram as if the distribution could be observed, but there are two difficulties with the real problem
    - In this figure, the input is one dimensional, but in general it is much higher dimensional and cannot be directly observed by humans.
    - In this figure, the distribution is known, but in general the distribution is unknown, and only a limited number of data is obtained by sampling from that distribution.

- dimension
    - Higher dimension than what humans can intuitively understand
        - For example, considering handwriting recognition, even a small 32x32 grayscale image has 1024 dimensions.
- In machine learning, the distribution of possible input values is unknown
    - If you create a random 32x32 grayscale image, it will almost never look like handwritten text
    - In other words, the actual "distribution of handwritten characters written in 32x32 grayscale" should be distributed in a very narrow subspace of the 1024-dimensional space.
    - Humans cannot well describe the shape of that distribution.

- Training data are sampling results from an unknown distribution
    - So it is not important to achieve 100% accuracy for the training data.
    - Need to have high accuracy for data that is not yet in hand and will be sampled in the future
    - How can its accuracy be measured?

- So, we put some of the input data separately, thinking, "Let's regard this as data that will be obtained in the future.
    - Observe how accurate the learning results are with that "separated data".
    - see  [[What it means to separate data]]

---
This page is auto-translated from [/nishio/機械学習はどうテストするのか](https://scrapbox.io/nishio/機械学習はどうテストするのか) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
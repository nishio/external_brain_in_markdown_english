---
title: "Curse of the dimension"
---

![image](https://gyazo.com/a584556b87390d4fbad2747e235a0017/thumb/1000)

- Humans have difficulty imagining beyond 2-4 dimensions.
- A lot of unexpected phenomena happen when you get dimensional.

- In [[higher dimensional space]], almost all points are far from the center
    - A point within distance 1 from the origin in one dimension is half of a point within distance 2
    - 1/4 in 2 dimensions
    - 1/8 in 3D
    - ...and the "percentage of close points" decreases exponentially as the dimension increases.

- The number of samples required for sampling increases exponentially.
    - In the case of machine learning, increasing the dimensionality of the machine deteriorates the accuracy.
    - Because the effect of insufficient sample size is more overwhelming than the improvement in accuracy due to the additional dimension.

![image](https://gyazo.com/934a40866acc18c6b266fdbb0c8b1ac2/thumb/1000)
[Chi-square distribution - Wikipedia](https://ja.wikipedia.org/wiki/%E3%82%AB%E3%82%A4%E4%BA%8C%E4%B9%97%E5%88%86%E5%B8%83)
- For 3 or more dimensions, the vector length mode is non-zero.
    - Condition that each axis follows a standard normal distribution with mode 0
        - [[chi-square distribution]]
    - This is related to "most points are far from the center."

    - [[Almost all vectors are orthogonal]]
    - [How similar are vectors with high cosine similarity (from Iwanami Data Science publication event) - Mi manca qualche giovedi`?](http://d.hatena.ne.jp/n_shuyo/20160401/cosine_similarity)
    - > 1000000 If you want to find the percentage of samples with a cosine similarity greater than 1/2,
    - >  0.06 (about 1/17) in 10 dimensions,
    - >  0.01 (about 1/100) in 20 dimensions,
    - >  0.0021 (about 1/480) in 30 dimensions,
    - >  0.00042 (about 1/2400) in 40 dimensions
    - > 100 In 100 dimensions, there were no points in the 10,000,000 sampled points where the cosine similarity was greater than 1/2.
    - Of course, in two dimensions, 33%.
    - [[Cosine similarity of 0.2 is extremely rare in higher dimensions]]
- relevance
    - [https://twitter.com/nishio/status/1258610796969340928?s=21](https://twitter.com/nishio/status/1258610796969340928?s=21)
        - [[diversity]]
    - If you take two random vectors in a high-dimensional space, the probability that they are nearly the same direction is very small compared to the probability that they are nearly orthogonal
    - As the number of dimensions (number of evaluation axes) increases, the probability of a state of complete superiority of one person's skills over another's decreases.
        - 100% in 1D, 50% in 2D, 25% in 3D
        - ![image](https://gyazo.com/1b7ed946d22e1cceca40118b9cc7ee6f/thumb/1000)

    - [[In high-dimensional space, the normal distribution is almost uniformly distributed on the hypersphere]]

- Almost every stop is a [saddle point
    - 99.8% in 10 dimensions

- There are few cases where only one particular axis is larger than the other.

- [[blind spot card]]  19

---
This page is auto-translated from [/nishio/次元の呪い](https://scrapbox.io/nishio/次元の呪い) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
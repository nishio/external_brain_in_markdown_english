---
title: "collaborative filtering"
---

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Explain collaborative filtering.

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>Collaborative filtering is a technology that analyzes user preferences and behavior patterns and uses this information to recommend items that users may be interested in. It is used primarily in recommendation systems and is used in a variety of places, including e-commerce sites and movie and music recommendation services.
...
Collaborative filtering requires data from many users and items and may not work well when data is scarce. This problem is known as the "[[cold start problem]]" and is particularly acute when making recommendations for new users or items. Content-based filtering or hybrid recommendation systems are sometimes used to address this problem.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I'm assuming this is a technique that has been advanced by the development of algorithms for large-scale matrix factorization, and you can explain that area.

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>The development of algorithms for large-scale matrix factorization has led to significant advances, especially in the area of recommendation systems. This approach, especially used in the context of collaborative filtering, provides more effective and scalable solutions when dealing with large numbers of user-item interactions and evaluations.

Basics of Matrix Decomposition
- Matrix decomposition is a technique that decomposes a large (usually very sparse) matrix of relationships between users and items into smaller [[low-rank]] matrices. This process allows for the discovery of hidden features and latent factors, thereby allowing users to make predictive evaluations on items they have not yet evaluated.

Algorithm evolution
- [[SVD]]（ [[singular value analysis]] ）：
    - An early matrix decomposition method, it decomposes a matrix into scalars, called singular values, and their corresponding vectors. However, SVD was not suitable for direct use in a recommendation system because it could not handle missing values.
        - 2010.08.31 [行列分解ライブラリredsvdを公開しました](http://hillbig.cocolog-nifty.com/do/2010/08/redsvd-aa59.html) by [[岡野原 大輔]]<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

- [[ALS]] ([[Alternate Least Squares]]):
    - ALS is a method that ignores missing values in the original matrix and uses one alternately fixed factor matrix to optimize the other. It is highly scalable because parallelization and distributed processing can be easily applied to large data sets.

- [[SGD]] ([[Stochastic Gradient Descent]]):
    - SGD is a method of computing gradients and updating parameters using randomly selected data points at each iteration; SGD works efficiently on large data sets and provides highly accurate recommendations when applied to matrix factorization problems.

Impact on progress
Advances in matrix factorization algorithms have enabled highly accurate and scalable recommendation systems for very large data sets. This has enabled major companies such as [[Netflix]] and [[Amazon]] to provide personalized recommendations that greatly enhance the user experience.

The evolution of these algorithms is not limited to the field of recommendation systems, but also provides a means of unraveling the latent structure of data in many other areas, such as data mining, natural language processing, and social network analysis.


---
This page is auto-translated from [/nishio/協調フィルタリング](https://scrapbox.io/nishio/協調フィルタリング) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Clustering axes"
---

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- Wouldn't it be possible to split the PCA appropriately by looking at the contribution ratio
    - Clustering axes
    - There are N axes, if you take two of each, there is no loss of information, but there are more of them.
        - <img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
            - A visualization that draws a scatterplot for each of the two axes of data is usually called a "[[pairplot]]" or "[[scatterplot matrix]]". This is a technique for plotting all variable combinations in a data set on two axes to visually see the relationships among variables.
            - For example, by sequentially assigning each variable to the X and Y axes and displaying scatter plots for all pairs at once, one can quickly see correlations and distribution patterns. This is especially useful for visualizing multidimensional data
    - In fact, there should be a combination of three or more that doesn't increase the loss too much.
    - Simplify the problem
        - I want to minimize the variance after the 3rd dimension, which is the "lost information" when I do a PCA on each of the N axes in two groups.
        - optimization problem
        - It's going to come down to existing algorithms.

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
The idea of clustering the PCA axes and dividing them appropriately while minimizing information loss is certainly interesting. The problem is simplified by considering the following
- Purpose: To minimize the loss of information (variance) in the third dimension and beyond when the N axes are divided into two groups and PCA is applied on each.
- Approach: Axes can be grouped by clustering similar axes based on the contribution ratio each axis explains. This allows for more efficient dimensionality reduction while minimizing information loss.
- Formulation as an optimization problem: To minimize the variance lost, it can be attributed to an optimization problem that aims to maximize the contribution ratio, using the partition of the axes as parameters. This approach could be attributed to clustering algorithms such as K-means, or to existing algorithms with ideas similar to variational methods.

This technique, which takes advantage of the contribution ratio of the axes, may be practically applicable as a new approach to dimensionality reduction.

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
The idea of clustering PCA axes and dividing them while minimizing information loss is related to several existing approaches. In particular, several optimization techniques are used in the areas of dimensionality reduction and clustering.

- [[Sparse PCA]]: This is a method that streamlines dimensionality reduction by focusing only on important axes, whereas standard PCA attempts to represent information using all axes. In axis partitioning and clustering, a similar approach can be used to group important axes for dimensionality reduction with less information loss
    - [Principal component analysis - Wikipedia](https://en.wikipedia.org/wiki/Principal_component_analysis)
            - Related [Scree plot - Wikipedia](https://en.wikipedia.org/wiki/Scree_plot)
        - [Sparse PCA - Wikipedia](https://en.wikipedia.org/wiki/Sparse_PCA)
            - > SPCA overcomes this disadvantage by finding components that are linear combinations of a small number of input variables (SPC).

    - [Everything you did and didn't know about PCA · Its Neuronal](https://alexhwilliams.info/itsneuronalblog/2016/03/27/pca/)

- Integration of clustering and dimensionality reduction: Methods that combine PCA and clustering to more efficiently represent the structure of data have also been studied. For example, one technique is to group data by clustering, followed by PCA to ensure that no information is lost from one cluster to another. This reduces information redundancy across clusters and increases the effectiveness of dimensionality reduction

- Hyperparameter optimization: The question of how many axes (principal components or clusters) to select during PCA or clustering can be viewed as part of hyperparameter optimization. Using cross-validation, methods have been proposed to select the optimal number of axes and clusters that minimize information loss

Combining these methods may minimize information loss in clustering and partitioning of axes.

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
Given a covariance matrix, the key to how to minimize the "lost information" when the axes are divided into two groups is to formulate the problem as an optimization problem. The problem may be solved by the following steps.
1. goal setting: 1.
    - We want to perform a PCA on each group and minimize the variance after the third dimension that is lost.
2. splitting of the covariance matrix:.
    - The covariance matrix represents the relationship between each dimension of the data. Dividing the axes into two groups corresponds to properly dividing the covariance matrix into two parts and maximizing the variance in each.
        - This reminds me of matrix blocking or low-rank approximation.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
        - <img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>Matrix blocking and low-rank approximation are very useful approaches to this problem. In particular, these methods play an important role in covariance matrix partitioning for dimensionality reduction and minimizing information loss.
            1. matrix blocking:.
                - The idea of dividing a covariance matrix into two groups is analogous to blocking a matrix. In matrix blocking, the matrix is divided into multiple parts and the features and relationships in each part are evaluated. Using this method, each block (group) can be adjusted to have an optimal structure, minimizing information loss.
            2. low rank approximation: 1.
                - The low-rank approximation can also be applied as a method to minimize the information lost when the covariance matrix is split. When the rank of the matrix is low, it indicates that the dimensions of the data can actually be represented by fewer variables. Therefore, the low-rank approximation can be applied to find the optimal partitioning such that the variance is minimized in the third dimension and beyond. This approach is closely related to methods such as matrix singular value decomposition (SVD).
            - Related Algorithms: 1.
                - Singular Value Decomposition (SVD): a low-rank approximation can be obtained by applying SVD to a covariance matrix. This allows for a partitioning of the matrix into lower-ranked forms, a partitioning that minimizes lost information.
                - Block Matrix Decomposition: This approach divides the matrix into blocks and applies PCA to each block. This approach reflects the structure of the data and increases the effectiveness of dimensionality reduction.
                - Matrix blocking and low-rank approximation are very powerful tools in dimensionality reduction and clustering problems, and can help optimize the covariance matrix for proper partitioning and reduced information loss.
3. quantification of information loss: (1)
    - The "loss of information" in each group corresponds to the variance in dimension 3 and beyond, which is not accounted for in the PCA. This depends on how much of the overall variance is captured by the selected principal components. For this reason, it is necessary to calculate the contribution ratio (percentage of variance explained) for each group and optimize the partitioning so that the contribution ratio in the third dimension and beyond is minimized.
- Algorithm
    - This optimization problem can be solved by combining a clustering algorithm (e.g., K-means) with PCA. Cluster the axes (variables) of the covariance matrix and apply PCA within each cluster. The goal is to divide the axes in such a way that the variance is minimized in the third and subsequent dimensions within a cluster.
        - Distance to axes must be defined to cluster axes with K-means<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
            - <img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
                - In order to cluster the axes with K-means, we need to define the distances to the axes. In this problem, an axis corresponds to each variable, so there are several possible ways to define the distance between variables.
                    - Distance based on covariance: 1.
                        - Correlation or covariance between variables can be used as a distance criterion. Specifically, covariance values between variables can be used to perform K-means clustering, where axes with high correlation are considered "close" to each other. In this case, the following distance indicators can be considered
                            - 1 - Correlation coefficient: The higher the correlation, the smaller the distance, and the lower the correlation, the larger the distance, so the correlation coefficient can be used to cluster axes.
                                - That's well and good,[[Agglomerative Hierarchical Clustering]] ならできそう<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
                            - Mahalanobis distance: This distance uses a covariance matrix and allows defining a distance that takes into account correlations between axes.
                                - That's not what I meant.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
                    2. principal component-based distance: (1)
                        - Based on the axes of the principal components obtained by PCA, the position of each variable in the principal component space can be used as a vector to calculate the distance between these vectors. For example, the distance between variables can be calculated using Euclidean distance or Cosine similarity, and K-means can be applied based on it.
                            - certainly<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
                                - Can the proximity of the PCA results to the first and second principal component axes be determined by the vector after the projection of the unit vector of each axis, without suddenly clustering the axes themselves?
                                - I'm not sure if this will end up doing one PCA and then choosing an axis that doesn't have a lot of information on it and PCAing it again.
                                    - Which leads us to [[Sparse PCA]] at the beginning here.
                                        - The axis with zero LOADING should be adopted for the second map.
                                    - After doing [[An experiment to let AI explain the principal component axis]], I thought this is not it.
                                - It would be, "Well, they all correlate strongly with the conservative-liberal axis."
                                - Or perhaps the first principal component axis is born as an averaging of the strongly divergent axes.
                                - Ha, is it better to preserve the first principal component axis and [[Birdwatch]]?
                    - Optimization after clustering: 1.
                        - Initial clustering is performed based on the distance between variables, and then optimization proceeds to minimize the loss of information (unexplained portion of variance) by PCA within clusters. Thus, by devising the definition of distance and grouping the axes appropriately, it is possible to suppress variance in the third dimension and beyond.
                    - These methods would allow us to define the distances to the axes and apply clustering by K-means.

5. practical approach
    - Specifically, the following algorithms are applicable
        - K-means clustering: The axes of the covariance matrix are divided into two groups using K-means and PCA is applied in each group.
        - Cross-validation: Find the optimal split using cross-validation to minimize the variance in the split group.
    - Thus, by clustering the axes of the covariance matrix and performing PCA within each cluster, it is possible to find the optimal split that minimizes information loss.

---
This page is auto-translated from [/nishio/軸をクラスタリングする](https://scrapbox.io/nishio/軸をクラスタリングする) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
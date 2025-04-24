---
title: "Accelerated Hierarchical Density Clustering"
---

![image](https://gyazo.com/bf5a96aabb558db383ae9e08f4b3107e/thumb/1000)
"Accelerated Hierarchical Density Clustering"
[https://arxiv.org/pdf/1705.07321](https://arxiv.org/pdf/1705.07321)

from [[HDBSCAN]]

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>This paper proposes a method to speed up the HDBSCAN* algorithm. The main points are:.
1. theoretical background:.
    - HDBSCAN* is a hierarchical extension of DBSCAN algorithm
    - Explains density-based clustering from three perspectives: statistical, computational, and topological
    - Solves problems with DBSCAN (difficulty in parameter selection, support for variable density clusters)
2. acceleration methods: 1.
    - Improve 3 bottlenecks: core distance calculation, [[minimum area tree]] (MST) construction, tree shrinkage
    - Efficient Nearest Neighbor Search Using Spatial Tree Algorithm
    - Improved [[Dual-Tree Boruvka]] algorithm to speed up MST construction
    - Improved computational complexity from O(N²) to about O(N log N)
3. experimental results
    - About 2 orders of magnitude faster than existing HDBSCAN* implementations
    - Execution time performance equivalent to DBSCAN
    - High efficiency compared to other major clustering methods except K-means
4. conclusions: 1.
    - Superior to DBSCAN in that parameter settings are intuitive and can accommodate variable density clusters
    - Execution speed has been improved to the same level as DBSCAN and can be the default choice for density-based clustering.
This research has solved the problem of computational cost, which was the main drawback of HDBSCAN*, and made the algorithm more practical.

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>The HDBSCAN algorithm is described in the paper from three different perspectives
- Statistical perspective:.
    - Starting with the assumption that the data are generated from an unknown density function
    - Construct a cluster tree from the density function f
    - Each branch of the tree represents a cluster, forming a hierarchical structure by density level λ
    - Based on Robust Single Linkage algorithm, using two parameters k and α
    - To reduce tree complexity, pruning was implemented by introducing a minimum cluster size m
- Computational perspective:.
    - Described as a natural extension of the DBSCAN algorithm
    - Using the concepts of core points and epsilon reachability
    - Introduces a new distance metric called mutual reachability distance
    - Apply single-linkage clustering to build hierarchical clustering
    - As a density-based approach, use λ = 1/ε to handle changes in density
- Topological Perspective:.
    - Applying topological data analysis methods
    - Use the concept of persistent homology
    - Constructed a single complex called the Lesnick complex
    - Describes cluster structure using sheaf theory
    - Evaluate the importance of clusters using persistent scores

These three explanations illuminate different aspects of the same algorithm
- Statistical explanations provide a theoretical foundation
- Computational description shows implementation details
- Topological explanation opens the possibility of mathematical generalization

Ultimately, these three approaches converge on the same algorithm, allowing for a deeper understanding of the algorithm by integrating perspectives from different research areas.

Each of these terms will be explained:

cluster tree
- Tree structure representing the hierarchical density structure of data
- Showing how clusters split and combine as density level λ changes
- Each branch of the tree represents one cluster
- ![image](https://gyazo.com/f234268f8f9b67bdb1b0808b04c7c593/thumb/1000)


Robust Single Linkage Algorithm


Improved version of conventional single linkage
More robust against noise
Two parameters, k and α, are used
More stable clustering by considering k neighborhoods around each point


core point


Important concepts in density-based clustering
Points with a minimum number k or more points within a neighborhood of epsilon radius
Represents the "core" point of the cluster


epsilon reachability


The concept of a relationship between two core points
If both points are contained within an ε-neighborhood of each other, they are "ε-reachable"
Used as a criterion for cluster formation


Mutual reachable distance


New distance metric between two points
An index combining the core distance (distance to the kth nearest point) and the actual distance
Distance measure considering density change of clusters


single-linkage clustering


A hierarchical clustering method based on the distance between the closest point pairs
Merging clusters using minimum distance
Characterized by the chaining effect (easy formation of elongated clusters)


topological data analysis


Mathematical methods to study topological properties of data
Analyze data shape and structure in terms of phase space
Extract invariant features for continuous deformations


persistent homology


A method for measuring the "lifetime" of topological features
Quantify the scale at which the feature is present
Helps to discern the essential structure of the data


Lesnick complex


A type of density-based mono-complex
Based on the Vietoris-Rips complex, incorporating density information
Computationally efficient structure.


simple substance (e.g. chemical)


A collection of single points, lines, triangles, etc.
Basic structures used in topological data analysis
A means of representing the topological structure of data


sheaf theory (cosmology)


Mathematical theory dealing with continuously varying sets on topological spaces
Used to describe continuous changes in cluster structure
Provides a more general mathematical framework


persistent score


Indicators to measure the importance of clusters
Quantifies at what density level clusters continue to exist
Used as a criterion for cluster extraction

These concepts are interrelated and form different aspects of the HDBSCAN algorithm. They play an important role in understanding the algorithm from statistical, computational, and topological perspectives.
---
This page is auto-translated from [/nishio/Accelerated Hierarchical Density Clustering](https://scrapbox.io/nishio/Accelerated Hierarchical Density Clustering) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
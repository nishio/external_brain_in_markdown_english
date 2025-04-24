---
title: "non-metric similarity"
---

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>What are some past studies on cases where similarity between concepts is not distance (A and B are similar, B and C are similar, but A and C are not similar at all, so the triangle inequality does not hold)?

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
In research psychology and cognitive science, it has long been noted that similarity as distance does not satisfy the axioms (symmetry and triangular inequality). As a representative example, in [[Tversky]]'s (1977) "[[Contrast Model]]", it was shown that even if A and B are similar and B and C are also similar, A and C are not necessarily similar, and it was argued that similarity may not obey triangular inequalities. Tversky & Gati (1982) reported experimental evidence involving triangular inequality violations, which was considered a universal feature in human conceptual similarity judgments.

In addition, the conceptual space theory of Gärdenfors (2000), non-Euclidean similarity models, and non-metric multidimensional scaling methods (Non-metric MDS) have also addressed the different nature of similarity relationships from metric distances. These studies suggest that psychological and conceptual similarity is not captured in a simple distance space, but has a more complex structure, including context-dependence and unbalanced weighting of elemental features.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Assuming such cognition in humans, it is not reasonable to embed natural language data in a vector space and cluster them based on distances in that space. What is the solution to this problem?

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>If the method of treating similarity directly as distance is inappropriate, the following alternatives are possible
- Non-Euclidean representation: non-standard geometric structures such as hyperbolic spaces and Riemannian manifolds are used to appropriately model relationships for which triangular inequalities do not necessarily hold.
- Use of non-distinctive similarity measures: direct introduction of similarity measures based on human perceptual features, such as Tversky's contrast model, can reflect similarity relationships that are different from metric distances.
- Learning-based similarity module: a neural network is trained to learn similarity relations under a given context and cluster them using computational methods other than simple distance operations on the embedding space.

These methods allow clustering to capture appropriate similarity structures even when natural language data cannot be reduced to a simple distance space.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
If it is possible to calculate [[non-metric]] similarity between two sets of data using LLM, etc., or if it is possible to perform an "operation to obtain the most similar", what specific analysis methods are possible?

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>If non-distance similarity (or "get the most similar" oracle-like operation) is possible, the following analysis methods are possible
- [[Non-metric Multidimensional Scaling Method]] ([[Non-metric MDS]]):
    - A method for obtaining placement from similarity data that does not assume metricity, allowing relationships between concepts to be visualized in a low-dimensional space to understand their structure.
- Graph-based method:
    - Construct graphs with similarity as edge weights, and use community detection and spectral clustering. These do not require triangular inequalities in distance and are more likely to tolerate asymmetry and non-metricity.
- Ranking and Top-k search:
    - If "most similar" can be generated directly, ranking analysis and Top-k neighborhood search become possible. This allows applications such as search, recommendation, and classification without reducing to distance space.
- Iterative reassessment with user feedback:
    - Interactively make similarity judgments using LLM and other methods, and use feedback to adjust and update similarity criteria. This allows for flexible fine-tuning of similarity concepts without being constrained by distance axioms.

In short, there are several methods that deal directly with non-metric similarity information, including non-metric MDS, graph methods, ranking-based methods, and dynamic methods that use feedback loops.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Learn more about 3.

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>If the "retrieve the most similar item" operation (Top-1 or Top-k search) is possible, analysis can be performed using ranking information and the neighborhood relationship itself, without having to deal with distance quantitatively. Specifically, the following methods and analyses can be considered.

- Relationship Structure Analysis by Ranking:.
    - If it is possible to "arrange items in order of increasing similarity" to a particular reference data, the rank list can be obtained for multiple reference data to estimate the structure of non-metric relationships among groups of items. Even if the similarity is not distance, it is possible to implicitly capture the non-metric latent space by aggregating the "more similar/less similar" information for individual reference points.

- Collective feature extraction by Top-k neighborhood search:.
    - By iteratively seeking the "top-k most similar to this item," we can define a "neighborhood set" around each item. By comparing and aggregating these Top-k neighborhood sets, cluster-like clusters can be found without direct distance measurement.
    - For example, starting with an item and collecting its Top-k similar items, and then performing a similar Top-k search for each Top-k similar item, a graph-like similarity network is formed. By searching for dense substructures within this network, an analysis similar to clustering can be performed.

- Ordinal Embedding with rank and Top-k information:.
    - There are methods that treat the given "similarity high rank" information as a relative similarity order between objects and obtain a spatial representation (e.g., an embedding that does not require the distance itself, but only preserves the rank relationship) that maximizes the consistency of the ranks.
    - In this case, information on the "most similar candidate" groups returned by the LLM can be used to acquire and integrate relative order relationships among items, ultimately constructing a latent space that is non-metric but reflects some sort of order (ranking structure).

- Applications for exploratory data analysis and information retrieval:.
    - By sequentially querying the "most similar cases" provided by LLM, etc. without necessarily assuming distance space in Nearest Neighbor Search, order-based information retrieval methods and hierarchical search (expanding candidates of related data to be referred to next based on rank), etc. can be realized. The following are some examples of the types of information retrieval methods that can be used.
    - Such an approach does not require specific distance figures to perform search, recommendation, and navigation tasks.

In summary, by using Top-k or ranking information,
- Compare ranking lists to get a non-metric view of the overall structure
- Forms a neighborhood graph structure and performs clustering-like analysis
- Seek a spatial representation based on [[Ordinal Information]] (ranking relations)
- Enables search and retrieval even when distance and metricity cannot be assumed
and other analytical methods will be possible.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Any recommendations for papers related to these?

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>The following are examples of related studies. All of them are helpful in understanding the analysis methods using non-metric similarity and rank/top-k information.

    - [[Non-metered MDS]]  (Non-metric Multidimensional Scaling):
    - Kruskal, J. B. (1964). Nonmetric multidimensional scaling: a numerical method. Psychometrika, 29(2), 115–129.
    - Classical method of obtaining spatial assignments from non-metric similarity data.

- Non-distance similarity model (Tversky's contrast model)
    - Tversky, A. (1977). Features of similarity. Psychological Review, 84(4), 327–352.
    - Representative example of a human similarity perception model that does not satisfy the triangle inequality.

- Ordinal Embedding
    - Jamieson, K., & Nowak, R. (2011). Low-dimensional embedding using adaptively selected ordinal data. 49th Annual Allerton Conference on Communication, Control, and Computing, 1077–1084.
    - A method of obtaining embedding using only ranking (rank relations).

- Graph-based method (community detection):.
    - Girvan, M., & Newman, M. E. J. (2002). Community structure in social and biological networks. PNAS, 99(12), 7821–7826.
    - Fundamental research on graph clustering using non-metric similarity indices as edge weights.

- Introduction to Information Retrieval in Top-k Search and Ranking Analysis:.
    - Manning, C. D., Raghavan, P., & Schütze, H. (2008). Introduction to Information Retrieval. Cambridge University Press.
    - Extensive coverage of basic techniques related to search, ranking, and Top-k queries.

These references provide a useful theoretical and empirical foundation for spatial representation, clustering, visualization, and exploratory data analysis using non-distance similarity data and "get the most similar object" operations.
---
This page is auto-translated from [/nishio/非計量類似度](https://scrapbox.io/nishio/非計量類似度) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
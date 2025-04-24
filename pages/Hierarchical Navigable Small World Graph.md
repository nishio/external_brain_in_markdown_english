---
title: "Hierarchical Navigable Small World Graph"
---

[[HNSW]] ([[Hierarchical Navigable Small World Graph]])
[1603.09320 Efficient and robust approximate nearest neighbor search using Hierarchical Navigable Small World graphs](https://arxiv.org/abs/1603.09320)
![image](https://gyazo.com/36a75328a6583c73ffe61844d1c4b105/thumb/1000)
- I thought it was a higher-dimensional version of [[Skip List]], and that's what the paper itself said.
    - [[skip list]]  /  [[skip graph]]

In a situation where we want to find a vector that is close to a given vector among a large number of vectors, a naive implementation would be O(N)
- Need a better way for cases where this is a problem.
- Conventionally, there was a method of spatial partitioning in 1 to 3 dimensions (kd-tree), but the vectors we are now envisioning have 1000 or so dimensions, so it is difficult to use.
- Performance of methods using proximity graphs comparable to kd-tree and [LSH
- As an improvement, [[Navigable Small World]] (NSW, also known as Metricized Small World, MSW) was released.
    - = graphs with logarithmic or polylogarithmic scaling of the number of hops during the greedy traversal with the respect of the network size
    - "An NSW graph is constructed by inserting a sequence of elements in random order and connecting them bi-directionally to the M nearest neighbors from the first inserted element."
    - "Links to the nearest neighbors of elements inserted at the beginning of the construction later become bridges between network hubs, maintaining overall graph connectivity and allowing logarithmic scaling of hop counts during greedy routing."
    - I'm not sure what you're talking about, so I'll go back to the paper.
    - [[Approximate Nearest Neighbor Search Small World Approach]]
        - The search method is to repeatedly transition from the start vertex to the "shortest distance adjacent vertex" and return it when the local minimum is reached.
            - Multisearch does it in parallel, starting from a random starting point
        - About adding vertices
            - ![image](https://gyazo.com/96e01867c473d89d66bda7ec12ea5845/thumb/1000)
            - 2: Perform multiple searches
            - 3: Follow the link one step further from the local minima
            - 4: Sort and link the k books from the nearest to the first.
            - In short, the points closest to the query in each randomly selected cluster are selected and connected in order of proximity, including their surroundings.
                - So if there is only one cluster nearby, only that cluster will have a link.
                - If a point in the query comes to a position that bridges multiple clusters, a link is generated to connect the clusters.
- And this proposal is a hierarchical version of this one.
    - > Maximum layer l is randomly selected with an exponentially decaying probability distribution.
        - This allows vertices that can enter higher layers to form a longer distance network
        - Vertexes that only enter the lower levels network with nearby vertices.
    - The search is hierarchical, with the upper layers searched, and then the results are searched in the lower layers using the results as a starting point.
        - After getting off at Narita Airport on an international flight, take the train to Tokyo Station and walk to the Cybozu office.
        - ![image](https://gyazo.com/e9a985adac272e88c5b6230e655c77ba/thumb/1000)


application
- > [[Qdrant]] currently only uses HNSW as a vector index. HNSW (Hierarchical Navigable Small World Graph) is a graph-based indexing algorithm.
- [[Pinecore]] works the same way [Hierarchical Navigable Small Worlds (HNSW) | Pinecone](https://www.pinecone.io/learn/hnsw/).
    - Most implementations of [[vector search]] do this

[[Hierarchical]]
[[Small World]]

---
This page is auto-translated from [/nishio/Hierarchical Navigable Small World Graph](https://scrapbox.io/nishio/Hierarchical Navigable Small World Graph) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
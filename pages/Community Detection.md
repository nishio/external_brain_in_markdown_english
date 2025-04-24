---
title: "Community Detection"
---

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
Community detection is a method for extracting densely connected groups of nodes (communities) in a network (graph) structure. For example, it is similar to identifying groups of close friends in a human network. Using algorithms ([[Modularity Maximization]], [[Louvain method]], [[Infomap]], etc.), the graph is partitioned into subgroups, and clumps with stronger internal connections than other groups are found. This makes it easier to interpret complex network structures in a straightforward manner and to understand topic clusters and related concept clusters.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Let me know the major method and implementation.

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>Examples of major community detection methods and implementations include the following
- [[Louvain Act]]
    - Feature: A fast heuristic method based on modularity maximization. Widely used for large graphs.
- Python implementation:
py

```
!pip install python-louvain
from community import community_louvain
partition = community_louvain.best_partition(G)
```


- [[Leiden algorithm]]
    - Feature: An improved version of the Louvain method, which is more stable and easier to obtain accuracy and modularity.
- Python implementation (using igraph):
py

```
!pip install python-igraph leidenalg
import igraph as ig
import leidenalg
g = ig.Graph.Read_Ncol("network.edgelist")
partition = leidenalg.find_partition(g, leidenalg.ModularityVertexPartition)
```


- [[Girvan-Newman method]]
    - Feature: A segmented algorithm that identifies community boundaries using edge-mediated centrality (edge betweenness). Although it is relatively computationally intensive and unsuitable for large-scale networks, it is theoretically straightforward.
- Python implementation (NetworkX):
py

```
import networkx as nx
from networkx.algorithms.community import girvan_newman
G = nx.karate_club_graph()
communities = next(girvan_newman(G))
```


- [[Infomap]]
    - Feature: Community detection with information flow optimization based on random walk.
- Python implementation (igraph):
py

```
import igraph as ig
g = ig.Graph.Read_Ncol("network.edgelist")
communities = g.community_infomap()
```


These methods provide an intuitive understanding of the internal structure of a given network and facilitate visualization and analysis of co-occurrence relationships and associations among texts.
---
This page is auto-translated from [/nishio/コミュニティ検出](https://scrapbox.io/nishio/コミュニティ検出) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
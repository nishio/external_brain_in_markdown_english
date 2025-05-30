---
title: 'Cutting the smallest cut is not "cutting an edge".'
---

Taking a graph "cut" literally as "to cut an edge" is a source of confusion in the context of minimum cut problems.

Definition of cut in graph: [cut (graph theory) - Wikipedia [https://ja.wikipedia.org/wiki/%E3%82%AB%E3%83%83%E3%83%88_(%E3%82%B0%E3%83%A9%E3%83%95%E7%90%86%E8](https://ja.wikipedia.org/wiki/%E3%82%AB%E3%83%83%E3%83%88_(%E3%82%B0%E3%83%A9%E3%83%95%E7%90%86%E8) %AB%96)]
> The bipartition (S, T) of the vertex V of a graph G(V, E) is called a cut.
It is better to view it as "painting the vertex in two colors, black and white", true to the definition.

- The [[minimum cut]] problem is to find a cut $(S, T)] such that the sum of the costs of the edges [$ (u, v) \in E$ such that $u \in S, v \in T$ is minimal. In other words, the problem is to "paint the vertices black and white so that the cost of the black and white edges is minimized.

Constraints that must be adhered to are often expressed in terms of edges with sufficiently large costs (hereafter referred to as "infinity edges"). For example, [[Project Selection Problem]].
![image](https://gyazo.com/b9559c8d3676a4a89942a16838a27ce1/thumb/1000)
The interpretation of "do not cut the infinity edge" is confusing because it makes it seem that the center portion is all connected. Instead, the vertices are painted separately.
I wrote black and white in the explanation so far, but the figure is red and white. Minimize the sum of the costs of the red and white sides.
In the first example, the cost is added to the edge of infinity because you have chosen project 1 but have not bought the required machine 2.
In the second example, only project 1 is selected. Project 2 is losing money because the necessary machines have been bought but not selected.
In the third example, project 2 is also selected.
![image](https://gyazo.com/a18e0dc6651304be872867f61f41f49d/thumb/1000)

The directed edge of the infinite cost is not "must not be cut" but "must not be painted red-white, but may be if it is white-red".
By putting up edges in both directions, "neither white-red nor red-white is allowed". This could be interpreted as "no cutting", but in general, there are not necessarily edges in both directions.

memo
- The second example doesn't make sense when you think of it as a flow.
    - To begin with, minimum cut is the problem of finding the smallest of the cuts
    - Not all of these "cuts" correspond to flow, only the smallest cut corresponds to the largest flow.

- [[Cut = Two-color painting of apex]]
---
This page is auto-translated from [/nishio/最小カットのカットは「辺を切る」ではない](https://scrapbox.io/nishio/最小カットのカットは「辺を切る」ではない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
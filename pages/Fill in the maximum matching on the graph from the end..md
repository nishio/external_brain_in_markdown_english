---
title: "Fill in the maximum matching on the graph from the end."
---

Set [[Maximum matching]] to [[fill in the blanks (at the end of a task)]] on the graph.
- ![image](https://gyazo.com/8f005eab033d686a1a4adbdafc70dcec/thumb/1000)

- When considering the maximum matching on a graph, a point with rank 1 can be considered to be included in the maximum matching
- The edge containing the point with rank 1 is called the "end edge", and the edge containing the other side of the edge is called the "next edge".
    - The next edge is zero or more in the general graph
- When you choose a certain maximum matching
    - 1: If neither the end edge nor the next edge is selected (or the next edge does not exist), then selecting the end edge increases the number of matches by 1
        - In other words, it was never a maximum match to begin with.
    - 2: When an edge is unselected and the next edge is selected, swapping selections does not increase or decrease
        - Thus, the exchanged ones are also the maximum matching
    - 3: Neither the end edge nor the next edge is selected for matching.
    - From 1 and 2, some of the largest matches always have end edges selected.
    - So you can select an edge and remove it.
    - In restricted graphs, this "edge of a blade removal" results in a new [edge of a blade
        - It does not hold true for general graphs.
        - Composed at the time of the tree: [[m_solutions2019D]].
        - Graphs whose maximal vertex is always rank 1: [[AGC029B]].
            - [[dominoes falling down a hill]] Everything will be resolved.
                - [[greedy algorithm]]
---
This page is auto-translated from [/nishio/グラフ上の最大マッチングを端から埋める](https://scrapbox.io/nishio/グラフ上の最大マッチングを端から埋める) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
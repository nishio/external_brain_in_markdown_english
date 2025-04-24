---
title: "✅ABC193F"
---

[F - Zebraness](https://atcoder.jp/contests/abc193/tasks/abc193_f)
![image](https://gyazo.com/e9f159c0e0b9070204a70e715eb1c8bd/thumb/1000)
- liquidation
        - [[Paint in two colors → Cut graphs]]
            - [[Cutting graphs]] is the division of a graph into two sets of vertices.
        - In other words, [[Paint in two colors]] and graph cuts are essentially the same thing
        - [[Maximum cut → Reverse one side if it is a two-part graph.]]
        - The minimum cut in the graph is solved by the maximum flow
        - However, this problem is [[maximum cut]] (set the number of different color problems to be increased)
        - Since the graph is a [[grid graph]], [[two-part graph]]
        - Reversing the fill of a vertex on one side of a bipartite graph will invert "same color or different color" for all edges
        - This changes "+1 if the colors are different" to "+1 if the colors are the same".
        - Minimize the edges that are different colors, i.e., minimum cut.
    - ![image](https://gyazo.com/eb51702b0e1c427719cdfb3c2ff4b3f9/thumb/1000)


----
from [[ABC193]]
ABC193F
[F - Zebraness](https://atcoder.jp/contests/abc193/tasks/abc193_f)
![image](https://gyazo.com/e9f159c0e0b9070204a70e715eb1c8bd/thumb/1000)
- Thoughts.
    - Width up to 100
        - 2^100 can't be held in memory, so DPing from above seems a bad idea.
    - Will it be a two-part graph since it will be painted in two colors?
        - Sometimes the only way to get the same color is to be next to each other.
    - Is there a greedy solution?
        - Sample passed, but when I submitted it, 20WA, I knew it was a bad idea.
    - Choose between two different checkerboard patterns for each connected mass of hatchets?
        - You can't do 2^2500 because you can make at worst 2500 more than 2 connected components.
        - Can each be calculated independently...
        - time-out
- Official Explanation
    - Maximum flow attributed to [Project Selection Problem
        - I knew this for knowledge, but it never occurred to me...
- Consideration again
    - First of all, I should have understood the setting "paint the vertices of the graph in two colors, black and white" as "think about the cut of the graph".
        - A cut of a graph is a graph whose vertex set is divided into two sets
    - After understanding that it's a cut, the association leads to "if it's a minimum cut, it can be solved with maximum flow".
    - This time, "+1 if the adjacent vertices of the graph have different colors.
        - I give positive credit to the fact that the color is different (it's a cut edge).
        - This would be a maximum cut problem, generally NP complete.
    - Use the fact that a grid graph is a bipartite graph
        - Invert the color of a vertex on one side of a bipartite graph
        - Then, the "is the vertex color different?" of all edges is inverted
        - Now we can set "-1" if adjacent vertices have different colors.
        - In the case of a grid graph, this means, in essence, that the vertices of the checkerboard pattern are inverted.
- mounting
    - Returns 0 when N=1
    - The Dinic implementation itself was buggy.
        - Isolated points in the graph will cause the number of vertices to be wrong and make the array smaller than it needs to be.
        - explicitly pass the number of vertices.
    - AC
py

```
def solve(N, world):
    if N == 1:
        return 0

    d = Dinic(N * N + 2)
    for u, v in world.allEdges():
        d.add_edge(u, v, 1, True)

    start = N * N
    goal = start + 1
    for pos in world.allPosition():
        x, y = divmod(pos, N)
        if world.mapdata[pos] != CHAR_Q:
            p1 = (world.mapdata[pos] == CHAR_B)
            p2 = ((x + y) % 2 == 0)
            if p1 ^ p2:
                d.add_edge(start, pos, 100)
            else:
                d.add_edge(pos, goal, 100)

    f = d.max_flow(start, goal)
    return (2 * N * (N - 1)) - f
```


---
This page is auto-translated from [/nishio/✅ABC193F](https://scrapbox.io/nishio/✅ABC193F) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
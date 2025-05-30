---
title: "✅ARC074D"
---

![image](https://gyazo.com/4d90135f13838ae486c33a1424fb914d/thumb/1000)

[F - Lotus Leaves](https://atcoder.jp/contests/arc074/tasks/arc074_d) diff: 2208
![image](https://gyazo.com/a72c294639d6c322d4bc4d623b87f6a0/thumb/1000)
- Thoughts.
        - [[minimum cut]] Known to be a scarecrow
    - Given a graph, the question is how many vertices should be removed to prevent reaching vertices S to T
    - If it is an "edge" rather than a "vertex" to be removed, it is a straightforward minimum cut problem
    - So we can [[Convert a vertex to an edge]].
    - ![image](https://gyazo.com/9fff8fc0b6b978f7275bebef8db70e1c/thumb/1000)
    - Set only the newly introduced red edge to weight 1, and set the other edges to weight infinite. If a minimum cut is required, the red edge will be cut the minimum number of times.
    - The other sides should be thick enough not to be cut off.
    - Unreachable when S and T are in a row, otherwise unreachable by removing all vertices at worst

1 MLE
[https://atcoder.jp/contests/arc074/submissions/20593919](https://atcoder.jp/contests/arc074/submissions/20593919)
- Poor library implementation or usage
- Worst case scenario is 20,000 vertices, 199 edges from 10,000 vertices.
- If you add row and column vertices, you get +200 vertices, with two coming out of each vertex...
- Too much memory is due to the hash table being a memory hog...

AC
- Since 200,000 edges seemed to be too much, and since the effect of increasing the number of vertices did not seem to be significant after trying it out in the [[Minimum Cut Study Session]], I decided to increase the number of vertices and reduce the number of edges.
- Instead of directly extending an edge from each vertex to a vertical or horizontal vertex, the vertices are now connected via a vertical or horizontal vertex.
        - [[Placing an intermediary in a many-to-many relationship]]
    - ![image](https://gyazo.com/418e454dc8ceb664691dcafdb6fc94a4/thumb/1000)

- This would reduce the worst-case scenario from 2 million to 30,000.
py

```
def solve(H, W, world):
    CHAR_S, CHAR_T, CHAR_O = b"STo"
    leaf = set()
    for pos in world.allPosition():
        if world.mapdata[pos] == CHAR_S:
            start = pos
        if world.mapdata[pos] == CHAR_T:
            goal = pos
        if world.mapdata[pos] == CHAR_O:
            leaf.add(pos)

    sy, sx = divmod(start, W)
    gy, gx = divmod(goal, W)
    if sy == gy or sx == gx:
        return -1

    INF = 10000
    d = Dinic(H * W * 2 + H + W)
    O_BG = H * W
    O_Y = H * W * 2
    O_X = H * W * 2 + H
    for pos in leaf:
        pos2 = pos + O_BG
        d.add_edge(pos, pos2, 1)
        y, x = divmod(pos, W)
        d.add_edge(pos2, y + O_Y, INF)
        d.add_edge(pos2, x + O_X, INF)
        d.add_edge(y + O_Y, pos, INF)
        d.add_edge(x + O_X, pos, INF)

    d.add_edge(start, sy + O_Y, INF)
    d.add_edge(start, sx + O_X, INF)
    d.add_edge(gy + O_Y, goal, INF)
    d.add_edge(gx + O_X, goal, INF)

    ret = d.max_flow(start, goal)
    return ret
```



---
This page is auto-translated from [/nishio/✅ARC074D](https://scrapbox.io/nishio/✅ARC074D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
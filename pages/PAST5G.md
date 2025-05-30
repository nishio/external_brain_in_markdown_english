---
title: "PAST5G"
---

[G - Snakes](https://atcoder.jp/contests/past202012-open/tasks/past202012_g)
![image](https://gyazo.com/3790c397c786b793094fb8a7167295bd/thumb/1000)
- Consider a graph with a square as a vertex and adjacent squares connected by edges.
    - The number of vertices is as small as 16 at the highest
- DFS "path through all vertices" starting at each vertex of the graph
    - Theoretical estimate of the computational complexity of this is not available, but it is small, so the decision was made based on the assumption that it would be possible.
- When the given square has 1 square, there are zero edges on the graph. This is the corner case with WA.
    - `(1)` treated with `(1)`.
    - but this is the problem with not making a list of vertices in the first place.
    - The set of starting points of an edge must be the set of vertices because the edge is bi-directional" - wrong, there are cases where there is no edge.
- The map reads [Putting a guard on when loading a map
    - Maybe the part about graphing by adjacency could be made into a library.
python

```
def solve(H, W, data):
    from collections import defaultdict
    # make graph
    edges = defaultdict(list)
    count = 0
    a_vertex = None
    for x in range(H):
        for y in range(W):
            v = W * x + y
            pos = WIDTH + 1 + WIDTH * x + y
            if data[pos]:
                a_vertex = v
                count += 1
                if data[pos + 1]:
                    edges[v].append(v + 1)
                    edges[v + 1].append(v)
                if data[pos + WIDTH]:
                    edges[v].append(v + W)
                    edges[v + W].append(v)

    if count == 1:  # (1)
        print(1)
        v = a_vertex
        x, y = divmod(v, W)
        print(x + 1, y + 1)

    for start in edges:
        visited = [False] * (H * W)
        path = []

        def visit(cur):
            visited[cur] = True
            path.append(cur)
            if len(path) == count:
                return True
            for next in edges[cur]:
                if not visited[next]:
                    r = visit(next)
                    if r:
                        return True
            visited[cur] = False
            path.pop()

        if visit(start):
            print(count)
            for v in path:
                x, y = divmod(v, W)
                print(x + 1, y + 1)
            return
```



---
This page is auto-translated from [/nishio/PAST5G](https://scrapbox.io/nishio/PAST5G) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
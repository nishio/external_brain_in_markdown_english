---
title: "edge depth first search"
---

![image](https://gyazo.com/1957f5e7122ed77931ef8d0dbf313033/thumb/1000)

[[ARC111]]D
- Given an undirected graph, we want to orient the edges so that they become strongly connected components.
- 1 is a vertex depth-first search, which means there are edges that cannot be passed.
- 3 is the correct edge depth-first search
- 2 is an inadvertent mistake.
    - I painted it at the right time to stack the edges to be visited in the future.
    - The edge coming out of the vertex of C is missing.

- 3
python

```
for v1, v2 in edgelist:
    if (v1, v2) not in answer:
        answer[(v1, v2)] = "->"
        answer[(v2, v1)] = "<-"

        def visit(e):
            (v1, v2) = e
            for v3 in edges[v2]:
                if v3 == v1:
                    continue
                if (v2, v3) in answer:
                    continue
                answer[(v2, v3)] = "->"
                answer[(v3, v2)] = "<-"
                visit((v2, v3))
        visit((v1, v2))
```

- 2
python

```
for v1, v2 in edgelist:
    if (v1, v2) not in answer:
        answer[(v1, v2)] = "->"
        answer[(v2, v1)] = "<-"
        stack = [(v1, v2)]
        while stack:
            v1, v2 = stack.pop()
            for v3 in edges[v2]:
                if v3 == v1:
                    continue
                if (v2, v3) in answer:
                    continue
                answer[(v2, v3)] = "->"
                answer[(v3, v2)] = "<-"
                stack.append((v2, v3))
```

- 2 implemented without recursive calls
    - Make the timing of the application the timing of actually following the edge.
    - Check that the already painted edge is not painted before applying it, since it may already be in the stack.
python

```
for v1, v2 in edgelist:
    if (v1, v2) not in answer:
        stack = [(v1, v2)]
        while stack:
            v1, v2 = stack.pop()
            if (v1, v2) in answer:
                continue
            answer[(v1, v2)] = "->"
            answer[(v2, v1)] = "<-"
            for v3 in edges[v2]:
                if v3 == v1:
                    continue
                stack.append((v2, v3))
```


- [[depth first search (search algorithm in AI)]]

---
This page is auto-translated from [/nishio/辺の深さ優先探索](https://scrapbox.io/nishio/辺の深さ優先探索) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "depth first search (search algorithm in AI)"
---

Depth-first search for trees should be distinguished from depth-first search for graphs.
The latter should avoid re-visiting a vertex that has already been visited
Easy to implement with recursive calls, but cost of function calls can be an issue

python

```
    def visit(v):
        for c in children[v]:
            parent[c] = v
            visit(c)

    visit(root)
```

python

```
    stack = [root]
    while stack:
        v = stack.pop()
        for c in children[v]:
            parent[c] = v
            stack.append(c)
```


[[DFS]]

---
This page is auto-translated from [/nishio/深さ優先探索](https://scrapbox.io/nishio/深さ優先探索) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
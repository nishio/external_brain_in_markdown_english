---
title: "PAST3E"
---

from  [[Third Algorithm Practical Skills Test]]
PAST3E
E Problem of coloring a graph. Write in a simple and concise manner so as not to include bugs.
python

```
from collections import defaultdict
N, NUM_EDGES, Q = [int(x) for x in input().split()]
edges = defaultdict(list)
for i in range(NUM_EDGES):
    v1, v2 = [int(x) for x in input().split()]
    edges[v1].append(v2)
    edges[v2].append(v1)
colors = [int(x) for x in input().split()]

for i in range(Q):
    # print(colors)
    f, *v = [int(x) for x in input().split()]
    # print(f, v)
    if f == 1:
        n, = v
        c = colors[n - 1]
        print(c)
        # sprincle
        # print(edges)
        for v in edges[n]:
            colors[v - 1] = c

    elif f == 2:
        n, c = v
        print(colors[n - 1])
        colors[n - 1] = c
```


---
This page is auto-translated from [/nishio/PAST3E](https://scrapbox.io/nishio/PAST3E) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
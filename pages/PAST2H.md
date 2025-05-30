---
title: "PAST2H"
---

![image](https://gyazo.com/d8cd95f94d454f735f18cfccd5356534/thumb/1000)
[H - 1-9 Grid](https://atcoder.jp/contests/past202004-open/tasks/past202004_h)

from  [[Second Algorithm Practical Skills Test]]

- Thoughts.
    - Troublesome to go through the same squares over and over again, want to avoid getting stuck in an endless loop when it is unreachable.
    - Think of it as having a floor of 0-9, not two dimensions.
        - Move one step from floor i and there is a staircase going up the floor only when the destination is i+1
        - Shortest path problem from S on floor 0 to G on floor 9
    - That's not the official explanation.
- Putting some time aside to think about it.
        - [[Dijkstra method]], so the edge can have a cost, so instead of "move one step from floor i and there is a staircase going up the floor only when the destination is i+1", I made it "the number i on floor i has an edge with cost 0 that goes up from the floor below".
    - Once the graph is constructed, just use the Dijkstra method to find the shortest distance.
- AC
python

```
def solve(HEIGHT, WIDTH, data):
    from collections import defaultdict
    edges = defaultdict(dict)
    W = WIDTH
    H = HEIGHT
    for level in range(10):
        for y in range(HEIGHT):
            for x in range(WIDTH):
                pos = x + y * WIDTH + level * WIDTH * HEIGHT
                v = data[y][x]
                if x < W - 1:
                    edges[pos + 1][pos] = 1
                if x > 0:
                    edges[pos - 1][pos] = 1
                if y < H - 1:
                    edges[pos + W][pos] = 1
                if y > 0:
                    edges[pos - W][pos] = 1
                if v == "S":
                    if level == 0:
                        start = pos
                elif v == "G":
                    if level == 9:
                        goal = pos
                else:
                    v = int(v)
                    if v == level:
                        edges[pos - W * H][pos] = 0

    return one_to_one(start, goal, 10 * W * H, edges)
```

- The official explanation is required by dynamic programming.
    - Computationally, Dijkstra is lighter.

---
This page is auto-translated from [/nishio/PAST2H](https://scrapbox.io/nishio/PAST2H) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "PAST4M"
---

![image](https://gyazo.com/3a479f29390ab0ae87d7f2087d5d94d4/thumb/1000)
from  [[Fourth Algorithm Practical Skills Test]]
[M - brush painting](https://atcoder.jp/contests/past202010-open/tasks/past202010_m)
- Thoughts.
    - The problem of finding the newest affecting query instead of actually painting it?
    - Query is 10^5, vertex is 10^5
    - How to find them.
- Official Explanation
        - [[time reversal (physics)]] 　 [[Consider operations in reverse order]]
        - [[Paint time reversal]]
        - [[Paths on the tree can be split by LCA.]]
- A new thought.
    - How do we retain information about the painting?
    - Is it ok to have a color for each vertex?
    - The number of pieces painted in one query is of logarithmic order, since the average height is logN, but of course there will be test cases with biased trees to make the worst linear order
    - Reversing the time axis, I want to skip over an area that has been painted once without painting it again.
    - How can we do that?
        - The bottom vertex of the paint should have an "already painted top edge".
    - If a "vertex that has already been painted" is encountered during the process, the top edge that has been painted is acquired.
        - If the top edge being painted is above the top edge of the area you are trying to paint, you are done.
        - If it's below, resume painting from the parent at the top edge of the painted area.
    - You can't just have a painted top end, you can't just have a painted bottom end.
        - Because the next query might start in the middle of the painted area.
    - How do you know the top end?
        - Just look at the top end you're trying to paint, and if it's painted, get that top end.
    - I'm in the mood to do something like this in natural language, so I'll show the rest properly in code.
- mounting
        - [[Do we paint the vertices or the edges?]]
        - I thought it was the pinnacle, but it's the edge.
            - [[Tree edges correspond to vertices other than roots]]
    - I was answering in vertex order when I should have answered in the order of the given edges.

AC:
python

```
def solve(N, Q, edges, QS, ordered_edges):
    from collections import defaultdict
    color = [0] * N
    uplink = [None] * N
    root = 0
    # graph to tree
    children, parents = graph_to_tree(N, edges, root)
    # ready lca
    construct(N, children, root, parents)

    def paint(start, end, c):
        cur = start
        while cur != end:
            if color[cur] == 0:
                color[cur] = c
                uplink[cur] = end
                cur = parents[cur]
            else:
                if query(uplink[cur], end) != end:
                    # uplink if avobe end
                    return
                cur = uplink[cur]

    for a, b, c in reversed(QS):
        a -= 1
        b -= 1
        lca = query(a, b)
        paint(a, lca, c)
        paint(b, lca, c)

    for frm, to in ordered_edges:
        if parents[frm] == to:
            print(color[frm])
        else:
            print(color[to])
```


I've been making these kinds of mistakes related to mistaking vertices and edges.
- After jumping to "END when painted in the past" with uplink, I'm moving on to more PARENT.
    - If it were vertex coloring, it would be correct, but since it is edge coloring, it is incorrect.
    - ![image](https://gyazo.com/c4a6f4511b8fe6c3a1fb93a59a34d4eb/thumb/1000)

python

```
def paint(start, end, c):
    cur = start
    while cur != end:
        if color[cur] == 0:
            color[cur] = c
            uplink[cur] = end
        else:
            if query(uplink[cur], end) != end:
                # uplink if avobe end
                return
            cur = uplink[cur]
            if cur == end: return
        cur = parents[cur]
```


---
This page is auto-translated from [/nishio/PAST4M](https://scrapbox.io/nishio/PAST4M) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
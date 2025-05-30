---
title: "PAST1K"
---

[K - Giant Corporations](https://atcoder.jp/contests/past201912-open/tasks/past201912_k)
- ![image](https://gyazo.com/735b48c1d33a9397fd177016e9fd6b8a/thumb/1000)
- Thoughts.
    - The problem of determining whether a is a descendant of b given a giant tree
    - O(NQ) when done naively.
        - If it's a balanced tree, it doesn't matter because it's on logarithmic order, but when it's very skewed, it's a problem.
    - I want to cache the calculation results, but naively caching the results will take up N^2 space, so it's no good
    - Cache unbranched paths?
        - No, there is a graph with N/2 branches followed by two branches.
        - Thought Branch A
    - Should I only cache when I'm biased?
        - Cache only points deeper than a certain level of pre-processing
        - No. You can make N/2 vertices deeper than N/2.
    - Thought Branch A
        - It would be nice if the determination of a later merge into a cached route could be done at a lower cost.
        - For example, tracing from a certain vertex to a root
        - At this time, the vertices traced in the array Ai for cache are recorded while incrementing
        - Writing cache number i in array B for finding a separate cache
        - After the second time, when tracing the parent, you can look at B to see if it's already cached in the constant order.
        - If it's already cached, we can look at the number of the target vertex in that cache and see how it compares to the number of the current vertex to see if it's ancestral or not.
        - The process of naively tracing a parent because it is not found in the cache can only happen at most N times.
        - Constant order after cache hit
        - PS: This method is not good for inputs that create a lot of fine caches, because the space calculation is too large.
    - Official Explanation
            - [[least common ancestor]] lca is required in logarithmic order
            - If lca(x, y) = x, then y is a descendant of x
            - Part of how to find the minimum common ancestor by doubling can be achieved.
                - First find the depth of each vertex, which is of linear order
                - Find 2^k parents ahead, linear order per k, logarithmic order for k values
                - Follow the deeper of the two given vertices to the parent and align the depths.
                - After this, a dichotomous search is needed to find the minimum common ancestor, but this time we only need to determine whether the shallower vertex is the minimum common ancestor or not.
        - another solution
            - Arrange vertices in order of destination
            - The vertices descended from a vertex are included in the interval starting at that vertex
            - If pos(x) < pos(y) <= end(x), then y is a descendant of x.
            - Constant Order
- AC
    - Change to 0-origin
    - Where a pointer is passed from each vertex to the parent, replace it with a pointer from the parent to the child
    - Find the depth of each vertex with DFS
    - Doubling to find 2^i vertices above
    - Find the depth difference d for each query and determine if the vertex d up from a matches b
python

```
def solve(N, PS, Q, QS):
    # PAST1K

    # to 0-origin
    PS = [p - 1 for p in PS]
    from collections import defaultdict
    children = defaultdict(list)
    for i, p in enumerate(PS):
        children[p].append(i)

    # calc depth
    depth = [0] * N

    def visit(v):
        d = depth[v] + 1
        for c in children[v]:
            depth[c] = d
            visit(c)

    root = children[-2][0]
    visit(root)

    # doubling
    parents = [PS]
    for _i in range(20):
        prev = parents[-1]
        next = [0] * N
        for i in range(N):
            next[i] = prev[prev[i]]
        parents.append(next)

    for a, b in QS:
        a -= 1
        b -= 1
        d = depth[a] - depth[b]
        if d < 0:
            print("No")
            continue
        # find d-th parent of a
        p = a
        for i in range(20):
            if d % 2:
                p = parents[i][p]
            d //= 2

        if p == b:
            print("Yes")
        else:
            print("No")
```


[[PAST1]]

---
This page is auto-translated from [/nishio/PAST1K](https://scrapbox.io/nishio/PAST1K) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
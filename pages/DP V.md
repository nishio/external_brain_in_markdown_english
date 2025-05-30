---
title: "DP V"
---

[V - Subtree](https://atcoder.jp/contests/dp/tasks/dp_v)
- Given a tree, the problem of finding the total number of fillings that can be reached from any black vertex to any black vertex through only black vertices
    - Am I understanding that you want the number of subtrees?
    - Oh, you want to answer "how many combinations such that vertex v is black? Simply asking for a subtree would increase the order by a factor of N, so you want to use a subproblem.
        - [[omni-directional wooden DP]]

- RE only where the problem is big enough to make it rustic.
    - I thought a dictionary with tuples as keys would be slower, so I used product integers as indexes.
    - N goes up to 10^5, so the square is 10^10 and MemoryError
        - There's a lot of memory on hand, so it works.
        - It was hard to find the cause of the problem because it would be RE instead of MLE.
    - RE [https://atcoder.jp/contests/dp/submissions/15106317](https://atcoder.jp/contests/dp/submissions/15106317)

- Even with modifications, TLE [https://atcoder.jp/contests/dp/submissions/15114039](https://atcoder.jp/contests/dp/submissions/15114039)
    - The tally becomes O(N) when there are many edges growing from one vertex.
    - Aggregation of a lot of things removed from a lot of things" requires using the result of an operation to reduce the amount of calculation.
    - Aggregation by multiplication cannot do "one back from all multiplied by one" because there is no inverse original to zero, while addition can do it because there is an inverse original....
    - So make the cumulative product from the front and from the back
    - I think this is always necessary with a graph that has no rank limit.

python

```
N = 700
xs = range(1, N + 1)

head = [0] * (N + 1)
cur = 1
for i in range(N):
    cur *= xs[i]
    head[i] = cur
head[-1] = 1

tail = [0] * (N + 1)
cur = 1
for i in range(N - 1, -1, -1):
    cur *= xs[i]
    tail[i] = cur
tail[-1] = 1

one_out_product = [head[i - 1] * tail[i + 1] for i in range(N)]
# print(head)
# print(tail)
# print(one_out_product)

if not"TEST":
    bluteforce = [1] * N
    for i in range(N):
        for j in range(N):
            if i == j:
                continue
            bluteforce[i] *= xs[j]

    #print(bluteforce)
    assert bluteforce == one_out_product 
```

You've made it, but when is the right time to execute this?

Read other people's code
- [https://atcoder.jp/contests/dp/submissions/14624575](https://atcoder.jp/contests/dp/submissions/14624575)
- Python  523msec
- I see, my code is divided into three categories "all white, black roots, and otherwise white roots" and propagates the latter two, but if the child's roots are white, the parent cannot be black, so it is always ignored in the final calculation, so there is no need to propagate it.
    - Just an update to "multiply by the value of the child and add 1."
    - Adding one is a pattern where the child is all white.
- Moreover, recursive calls are not necessary, and First, it records the order traced by the width-first search. Also, at that time, the opposite edges are erased.
- ![image](https://gyazo.com/b910e1af8eb9355d9717ec6f26604f7f/thumb/1000)


python

```
def solve(N, M, edges):
    # convert bidirectional graph to tree
    root = 1
    parent = [-1] * (N + 1)
    to_visit = deque([root])
    bfs_visited_order = []
    while to_visit:
        cur = to_visit.popleft()
        bfs_visited_order.append(cur)
        for child in edges[cur]:
            if child == parent[cur]:
                continue
            parent[child] = cur
            edges[child].remove(cur)  # remove back-link
            to_visit.append(child)

    # up-edge: v -> parent[v]
    # default: if no child, one black, one white (1 + 1)
    # f(x) = prod(f(c) for c in children) + 1
    upedge = [0] * (N + 1)
    # stores multiply result (1 is unity)
    multiply_of_upedge = [1] * (N + 1)
    for cur in reversed(bfs_visited_order[1:]):
        # visit vertexes except root, in reversed order
        upedge[cur] = multiply_of_upedge[cur] + 1
        p = parent[cur]
        multiply_of_upedge[p] *= upedge[cur]
        multiply_of_upedge[p] %= M
    # root: multiply children and don't add one
    # the one is "all-white" pattern
    upedge[root] = multiply_of_upedge[root]
    final_result = upedge[:]

    # down-edge: parent[v] -> v
    downedge = [1] * (N + 1)
    for cur in bfs_visited_order:
        prod = 1
        # left-to-right accumlated products (* downedge[cur])
        for child in edges[cur]:
            downedge[child] = prod
            prod *= upedge[child]
            prod %= M
        # multiply right-to-left accumlated products
        prod = 1
        for child in reversed(edges[cur]):
            downedge[child] = (downedge[cur] * downedge[child] * prod) % M + 1
            prod *= upedge[child]
            prod %= M

        for child in edges[cur]:
            # update final result
            final_result[child] = (
                multiply_of_upedge[child]
                * downedge[child]) % M

    return final_result[1:]
```

[https://atcoder.jp/contests/dp/submissions/15122587](https://atcoder.jp/contests/dp/submissions/15122587)

---
This page is auto-translated from [/nishio/DP V](https://scrapbox.io/nishio/DP V) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
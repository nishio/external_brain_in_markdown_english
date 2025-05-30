---
title: "omni-directional wooden DP"
---

When doing [[wood DP]] with all vertices as roots, the technique is that if you use the directed edges as the domain, you can use the result and it will be O(N).
![image](https://gyazo.com/5f02c5706cebeceb42cc0f5e7ed2843f/thumb/1000)
- The usual tree DP is O(N) with N number of edges for a particular root.
    - Since it is a tree, the edge is a vertex - 1 vertex
- If we want to do tree DP for all vertices, a simple iteration will result in an order of N^2
    - Reusing the results from the first tree DP would be 2N steps.
- In the figure, "Find the longest path through A" is first obtained with a 7-step tree DP
    - Find the depth of a child's tree from a particular root, and add the two from the larger of the two, the longest path through its apex.
    - Next, when solving "Find the longest path through B," the result of tree DP for A is reused and completed in one step
- In order to have the result of the calculation in a form that is easily reusable, the directed edges, not the vertices, must be the domain of definition.
    - E when A is the parent and E when F is the parent are two different things.
    - ![image](https://gyazo.com/7b2da7c244be0051fd9755847b7e7d22/thumb/1000)
    - In other words, when it is a single tree DP, there is a one-to-one correspondence between "the root of a directed edge" and "a vertex other than the root", so the vertex can only be the domain of definition.
    - It works even if you have a directed edge literally as a "tuple of start and end points," but it is easier if you divide the edge into two parts, "study approaching the root" and "edge moving away from the root," because the start and end points correspond one-to-one to vertices other than the root, respectively.
        - The implementation I saw first did a breadth-first search of the undirected graph from the vertices to remove "edges approaching the root."
        - Store the search order so it can be implemented without recursive calls
        - The first tree DP can be processed in reverse order with width priority, the next phase is completed in forward order.
- Need to be creative in aggregation
    - Suppose a vertex has 10,000 edges connected to it (rank 10,000), the value of the directed edge leaving this vertex is obtained from the remaining 9999 edges.
    - If this aggregation process is of order of rank, then it is of order O(N^2), where N is the number of ranks.
        - It's hard when a graph has edges concentrated on a single vertex.
        - When you say the word "tree" naively, what comes to most people's brains is a graph with a small rank number.
        - The test case will exploit this pattern as long as it is not explicitly excluded in the problem condition.
    - The technique to make this tally O(1) has nothing to do with the omnidirectional tree DP
        - Depends on the nature of the aggregation process
        - I want to take the sum of N numbers minus one.
            - Keep the sum total and subtract one.
            - To generalize, this can be used for "binary operations where [[inverse element]] exists.
        - I want to take the product of N numbers minus one.
            - Multiplication has no inverse element (not divisible by zero)
                - If [[unit element]] exists and [[associative law]] holds, then [Cumulative product from left to right
            - Even with the surplus, it's still in this class.
- After the calculation that gathers to the root, "calculate the arrow down to the child in O(N)" above, starting from the root.
    - ![image](https://gyazo.com/9cdfd1567858c3214c5f7147643700fe/thumb/1000)
    - The figure shows a lump sum calculation for A's children.
    - Then children B, D, and E have all the information they need to produce the final result because all the arrows that collect there have been determined.
    - By repeating this process, the answer is determined in the order of breadth-first search

reference
- [Tree DP and Omnidirectional Tree DP from basics to abstraction [[Competition Programming]] | Algorithmic Logic []](https://algo-logic.info/tree-dp/)
- [About †Omnidirectional Tree DP† - Diary of ei1333](https://ei1333.hateblo.jp/entry/2017/04/10/224413)
- [F - Distributing Integers](https://atcoder.jp/contests/abc160/tasks/abc160_f)
- [https://maspypy.com/atcoder-参加感想-2019-03-28abc-160](https://maspypy.com/atcoder-参加感想-2019-03-28abc-160)

- [[dynamic programming]]
---
This page is auto-translated from [/nishio/全方位木DP](https://scrapbox.io/nishio/全方位木DP) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
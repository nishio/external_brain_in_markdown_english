---
title: "Attributed to the least-cost stream"
---

![image](https://gyazo.com/4b7d4a231225f9f2363bf0e692829b53/thumb/1000)
Organize notation and draw the flow of various problems.

itemized discussion
- ABC004D [D - Marble](https://atcoder.jp/contests/abc004/tasks/abc004_4)
    - ![image](https://gyazo.com/38dcd4abb0b8f661eb30039f293a802c/thumb/1000)

    - Xi stones are placed in three locations.
    - Assign up to one of these to an unspecified number of squares.
        - The problem condition is infinite number of pieces, but realistically, a number about the sum of Xi is sufficient.
    - Cost Cij is the distance from the place where it is located to the destination
- [[PAST3O]]
    - ![image](https://gyazo.com/c243561fb3069ff0f7a2c41046325ef2/thumb/1000)
        - ![image](https://gyazo.com/11af29d8073e126040a8d77a4f22b2d8/thumb/1000)

    - Assign N locations for M objects in each of the three rounds
    - At this time, the reward Rij is obtained
    - However, the cost Djk depends on how many k were finally assigned to location j
    - This cost is progressive.
    - So it can be expressed using Cjk=Djk-Dj(k-1)
        - Because they are chosen from the cheapest
        - [[Least cost flow where costs are not proportional to flow rate]]
        - [[Progressive cost expressed as a difference]]
- [[ACLPC E]]
    - ![image](https://gyazo.com/eaaba4778f81bf4f4751b1e923ffae74/thumb/1000)
    - Up to K in the same row
    - = Select up to K from N locations
        - It is important to note that not just K pieces
        - Acknowledge the choice not to choose by creating a side path.
        - [[Two-dimensional cells are bipartite graphs]]
        - The squares correspond to the edges of a bipartite graph.
- [F - Three Knights and a Dog](https://atcoder.jp/contests/maximum-cup-2013/tasks/maximum_2013_f)
    - [Maximum-Cup 2013: F - Three Knights and a Dog - kmjp's blog](https://kmjp.hatenablog.jp/entry/2013/11/17/1030)
    - ![image](https://gyazo.com/92ae403683bc716bc08c1a73ec2e8528/thumb/1000)
    - Choose the one with the smallest cost among those with the largest rewards to be obtained.
    - The number of choices is M, the number of pieces chosen L=min(N, M)
    - Rewards are used to construct the graph instead of putting them on the edges.
        - Sort in order of reward Rj, and select the remaining L-A pieces from the B pieces with the same score as the Lth piece, with A as the number of pieces to be selected with a definite score higher than the Lth piece.
- [No.1301 Strange Graph Shortest Path - yukicoder](https://yukicoder.me/problems/no/1301)
    - undirected graph
    - Shortest path from vertex 1 to N and back to 1
    - Can go through the same side twice.
        - 1st cost ci, 2nd cost di, di>=ci
    - ![image](https://gyazo.com/0ab440e908ffd90d188962117aa3ec02/thumb/1000)
    - Flow rate 2
    - Why is this okay?
    - ![image](https://gyazo.com/671dddb208ffc7a1f3033431de840421/thumb/1000)
    - If you're going through an edge only once, you can go through in the opposite direction for the same cost.
    - When you're going through it twice, the opposite side is gone, so it costs d
    - Divide the cost by 2 through flow rate 2 to get what you want to ask for.
relevance
    - [[least-cost current]]
    - [[maximum current]]
- Comes down to the shortest path problem.
---
This page is auto-translated from [/nishio/最小費用流に帰着](https://scrapbox.io/nishio/最小費用流に帰着) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
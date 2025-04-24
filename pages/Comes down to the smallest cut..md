---
title: "Comes down to the smallest cut."
---

Issue List
- [[✅ARC074D]] [F - Lotus Leaves](https://atcoder.jp/contests/arc074/tasks/arc074_d) Difficulty: 2208
- [[KUPC2016E]] [E - fence](https://atcoder.jp/contests/kupc2016/tasks/kupc2016_e) Difficulty: unknown
- [[✅ABC193F]] [F - Zebraness](https://atcoder.jp/contests/abc193/tasks/abc193_f) Difficulty: 2475 AC
- [[✅ARC085E]] [E - MUL](https://atcoder.jp/contests/arc085/tasks/arc085_c) Difficulty: 2571 AC
- [[ARC031D]] [D - good shopper](https://atcoder.jp/contests/arc031/tasks/arc031_4) Difficulty: 2825 Consideration OK
- [[ARC107F]] [F - Sum of Abs](https://atcoder.jp/contests/arc107/tasks/arc107_f) Difficulty: 3130 Consideration OK
- [[WUPC2019F]] [F - RPG](https://atcoder.jp/contests/wupc2019/tasks/wupc2019_f) Difficulty: unknown Consideration OK
- [[💻KUPC2017H]] [H - Make a Potion](https://atcoder.jp/contests/kupc2017/tasks/kupc2017_h) Difficulty: unknown Integer
- [[TTPC2015L]] [L - graph coloring](https://atcoder.jp/contests/ttpc2015/tasks/ttpc2015_l) Difficulty: unknown


- The Problem of Finding the Best Choice
    - Typical pattern
        - Paint a 100 x 100 grid in two colors.
            - [[✅ARC074D]], [[✅ABC193F]]
        - There are about 100 options for two choices.
            - The cost and rewards will depend on that choice.
            - There is a dependency between choices.
    - Represent the selection with a two-color fill of the vertex.

    - We call these paint colors S and T.
    - Introduce two apex starts and a goal
        - These are painted with S and T, respectively.
        - The vertices themselves are sometimes represented as S and T. I use start and goal in the code, and S and T in the diagram.
    - If it's a two-choice option, it's a natural response.
    - Can be expressed in more than three choices [[ARC107F]].
- The basic form of the minimum cut is "if the color of both ends of a side is different, a cost will be incurred" and "we want to minimize the cost".
    - If you subtract an edge of weight x from vertex S to vertex v, it means "pay cost x if v is T".
    - If you subtract an edge of weight x from vertex v to vertex t, it means "pay cost x if v is S".
    - If it's a question of maximizing scores, make "score reduction" a cost.
        - Consider the case where all scores are obtained to be the offset, and the decrease from that offset to be the cost
    - If the cost is incurred when both ends of a side are the same color [[Invert one side of a bipartite graph]].
    - I don't care that the edge values are negative in this phase, because I'll deal with that later.
- Express the constraint "if vertex u is S, then vertex v is also S" by making the weight of edge uv sufficiently large
    - If we make it bidirectional, we get the expression u=v.
- Once the graph is constructed, solve for the maximum flow
    - However, it does not correspond well with negative cost edges.
        - It becomes unintelligible around the negative capacity.
    - So we'll work on removing the negative edges here.
    - Note the vertex v to which the negative edge -x is connected
        - Vertex v color is either S or T
        - Make it cost an additional x either way.
            - Just add the additional cost of x to the sides Sv and vT
        - Now the negative side disappears.
        - This operation increases the offset by x
        - This "add x" does not have to be exactly x, so if you are not comfortable with exactly x, you can just give a large enough value as you see fit.
- Once this is done, use an algorithm such as Dinic to find the maximum flow f from the start to the goal.
    - Just read cost as capacity.
    - The answer that offset - f seeks


---
- [[Cutting the smallest cut is not "cutting an edge."]] I think I can organize it a little better now that I've noticed
    - It might be good to re-explain some of the problems mentioned in [[Solve the "Burn Fill Problem" using the smallest cut...]] using vertex painting instead of edge cutting.
    - But I'd prefer a problem I can solve with atcoder anyway.
- [https://blog.hamayanhamayan.com/entry/2017/05/09/120217](https://blog.hamayanhamayan.com/entry/2017/05/09/120217)
    - [[✅ARC074D]] [F - Lotus Leaves](https://atcoder.jp/contests/arc074/tasks/arc074_d) diff: 2208
    - [[💻KUPC2017H]] [H - Make a Potion](https://atcoder.jp/contests/kupc2017/tasks/kupc2017_h)
    - [[ARC031D]] [D - good shopping](https://atcoder.jp/contests/arc031/tasks/arc031_4) diff: 2825
    - [[TTPC2015L]] [L - Graph coloring](https://atcoder.jp/contests/ttpc2015/tasks/ttpc2015_l)
    - [[KUPC2016E]] [E - fence](https://atcoder.jp/contests/kupc2016/tasks/kupc2016_e)
    - [[✅ARC085E]] [E - MUL](https://atcoder.jp/contests/arc085/tasks/arc085_c) diff:2571
    - [https://atcoder.jp/contests/qupc2014/tasks/qupc2014_h](https://atcoder.jp/contests/qupc2014/tasks/qupc2014_h)
- [https://drken1215.hatenablog.com/archive/category/最小カット](https://drken1215.hatenablog.com/archive/category/最小カット)
    - [AtCoder ARC 074 F - Lotus Leaves (yellow, 800 points) - Kenchon's Competitive Pro Devotion Record](https://drken1215.hatenablog.com/entry/2020/01/29/011100)
    - [AtCoder ARC 085 E - MUL (orange, 700 points) - Kenchon's Competitive Pro Devotion Record](https://drken1215.hatenablog.com/entry/2019/12/17/113800)
    - [Waseda University Programming Contest WUPC 2019 F - RPG - Kenchon's Competitive Professional Devotion Record](https://drken1215.hatenablog.com/entry/2019/03/11/123200)
    - +4 AOJ
- [[✅ABC193F]] diff:2475
- [[ARC107F]] diff: 3130
    - [https://maspypy.com/atcoder-参加感想-2020-10-31arc107](https://maspypy.com/atcoder-参加感想-2020-10-31arc107)


---
This page is auto-translated from [/nishio/最小カットに帰着](https://scrapbox.io/nishio/最小カットに帰着) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
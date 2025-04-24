---
title: "WUPC2019F"
---

[F - RPG](https://atcoder.jp/contests/wupc2019/tasks/wupc2019_f)
![image](https://gyazo.com/b7d9e87ab5927f6a16affa0feaadd2e2/thumb/1000)
- Thoughts.
    - Known to result in minimum cuts
    - There are two states of "fatigue" and "energy" that make the cut honestly.
    - The state of the graph changes as it passes through vertices.
        - That is, there are "before" and "after" states of the vertex.
            - [[Convert a vertex to an edge]]
    - Vigor is S because it starts in a state of vigor.
    - How to express that the state at the time of clearing can be either?
    - Summarize the considerations to this point in a diagram
        - In a combat situation, the front is vigor and the rear is fatigue.
        - In recoverable situations, you can go from fatigue to recovery and pay the cost.
        - ![image](https://gyazo.com/ffa8cbd1d6ea78c3997491877cb77fb4/thumb/1000)
    - No closed path" condition for the shape of the graph
        - No closed roads, but there is a merge, right?
        - There is a confluence in input example 1.
        - What happens when they join in different states?
        - If one of the upper reaches is Genki S, then its apex is also Genki S."
            - Fatigue T only when everything upstream is fatigue T."
            - If either of them is S, then it is S." Just stretch the infinity edge.
            - But all by itself, it can be both S and T when it's all T.
            - ![image](https://gyazo.com/04ed2dd16f5371ca5aca65cf11312711/thumb/1000)
        - Ah, okay, I misunderstood the problem constraint.
            - Constraint that whatever path the user takes, he/she goes through the recovery point before the battle.
            - In other words, if there are two ways and one of them is T, then after the merge, T
            - If it's all S, it can be either S or T, but it doesn't matter because T only increases the cost.
                - (I want to be a little more clear here.)

---
This page is auto-translated from [/nishio/WUPC2019F](https://scrapbox.io/nishio/WUPC2019F) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
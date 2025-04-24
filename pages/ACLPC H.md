---
title: "ACLPC H"
---

![image](https://gyazo.com/8226413287676381d2b6bd90036798ef/thumb/1000)

from [[AtCoder Library Practice Contest]]
ACLPC_H
[H - Two SAT](https://atcoder.jp/contests/practice2/tasks/practice2_h)
- ![image](https://gyazo.com/5e370ce12c72189acac9ebddccbfd576/thumb/1000)
    - Two-SAT can be solved by using [[strongly-coupled component decomposition]] [[2-SAT]]
- Two-SAT is a problem to find the solution of a logical equation in the form of an OR of two terms connected by an AND.
    - But in the case of problem H, it would be easier to understand to construct the graph directly using that principle than to use Two-SAT.
- Principle of attributing Two-SAT to strongly connected component decomposition
    - If A, then B. The relationship can be thought of as an edge in a directed graph.
    - Considering the strongly connected components of this graph, if any one of them is True, then all of them are True, so they are either all True or all False
    - ![image](https://gyazo.com/8226413287676381d2b6bd90036798ef/thumb/1000)
    - OR can be converted to "if" by [$ (A \vee B) = (\neg A \Rightarrow B) \wedge (\neg B \Rightarrow A)
    - So, if we construct the graph, perform a strongly connected component decomposition, and assign a boolean value to each component, we can obtain a solution
        - If A and not A are in the same component, it is unsatisfiable, if they are different components, we can say True when A is first.
            - I can't properly show that this allocation will not cause problems. I don't think the general graph is good enough.
- Returning to the specific problem H, we can construct a graph with the "if" in "If a flag is placed at Xi, then a flag must not be placed at a distance less than D" as an edge and decompose it into strongly connected components
---
This page is auto-translated from [/nishio/ACLPC H](https://scrapbox.io/nishio/ACLPC H) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Project Selection Problem"
---

- There are N projects.
    - Doing project i yields income [$ r_i
- There are m machines.
    - Buying machine j costs [$ c_j
- In order to do a project, you have to buy the machinery needed for that project.
- Which project should I choose to maximize profit = revenue - cost?

    - Solvable by [[minimum cut]] ( [[maximum flow]])
    - ![image](https://gyazo.com/052e99dda764a20363b0fea423f5cf79/thumb/1000)

    - [[Cutting the smallest cut is not "cutting an edge".]]
    - Easier to understand if interpreted as vertex painting
    - The project painted in the same color as the start is the "selected project"
    - Machines painted the same color are "purchased machines."
    - ![image](https://gyazo.com/9903f6866f0e9937fc6ee794b5f23090/thumb/1000)
    - In the figure, -p should be read as r
    - ![image](https://gyazo.com/a18e0dc6651304be872867f61f41f49d/thumb/1000)


----
The following explanation is [[Cutting the smallest cut is not "cutting an edge"]]. This is not a good explanation because it was written before I understood

- There are N projects.
- There are m machines.
- Project requires some machinery
- Choosing project pi yields income r(pi)
- Buying the required machine qj costs c(qj)
- Which project should I choose to maximize profit-cost?
    - Solvable by [[minimum cut]] ( [[maximum flow]])
    - ![image](https://gyazo.com/22cdb18d63c33e3a302b1e21192343e7/thumb/1000)
- Express the constraint, "If a project is selected, we must buy the necessary machinery," with the edge of infinity
    - Either the right or left side must be cut.
    - View not cutting the project edge as a "project choice".
    - Cutting the edge of a machine is viewed as "buying a machine".
    - If you have selected a project (not cutting an edge), you need to buy a machine (cutting an edge).
    - Not choosing a project = less income, buying a machine = cost, want to minimize this sum -> minimum cut
    - ![image](https://gyazo.com/978ffe04cab172fb6ea7a364eb743e4b/thumb/1000)

- It can be interpreted as a question of choosing between two options.
        - [[LP, Graphs and Formulations]]

[https://en.wikipedia.org/wiki/Max-flow_min-cut_theorem#Project_selection_problem](https://en.wikipedia.org/wiki/Max-flow_min-cut_theorem#Project_selection_problem)
- [[maximum flow]]

---
This page is auto-translated from [/nishio/Project Selection Problem](https://scrapbox.io/nishio/Project Selection Problem) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
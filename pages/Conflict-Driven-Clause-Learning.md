---
title: "Conflict-Driven-Clause-Learning"
---


CDCL is an algorithm that extends the Davis-Putnam-Logemann-Loveland (DPLL) method to solve SAT problems in an exploratory manner, and when a Conflict occurs, it analyzes the cause and learns a new Clause to streamline the next search.
- CDCL is very widely used in the implementation of [[SAT solvers]], and modern solvers (e.g., [[MiniSAT]], [[Glucose]]) are based on this algorithm.

Operation Flow
- Decision: The decision is made by the
    - Assume values for variables and construct a search tree.
- Propagation: The
    - Determine values for other variables based on assumed values (unit propagation).
- Conflict Detection.
    - When discrepancies occur, the clauses causing the discrepancies are analyzed.
- Learning (Clause Learning):.
    - The causes of discrepancies are analyzed and new clauses (study clauses) are generated.
    - This ensures that the same inconsistencies are not explored again.
- Backtracking:.
    - Go back forward from where the discrepancy occurred and attempt a new branch.
- CDCL performs "nonchronological backtracking" based on the cause of the discrepancy, rather than simple backtracking.


---
This page is auto-translated from [/nishio/Conflict-Driven-Clause-Learning](https://scrapbox.io/nishio/Conflict-Driven-Clause-Learning) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
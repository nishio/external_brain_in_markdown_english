---
title: "Least cost flow is a linear programming problem"
---

- [[least-cost current]] is a [[linear programming problem]].
minimize
- $\sum_{(i,j)\in E} c_{ij} x_{ij}$
subject to
- $0 \le x_{ij} \le u_{ij}$
- $\sum_i x_{ik} - \sum_j x_{kj} = b_k \quad (\forall k \in V)$
where
- c: cost
- x: flow
- u: capacity
- b: Supply and demand
    - Special form with one positive vertex and one negative vertex if the start and goal are such that there is one point

[Mathematical Programming, Vol. 10, Chapter 3, Network Planning Minimum Cost Flow Problem and Negative Closure Removal Method](http://www.dais.is.tohoku.ac.jp/~shioura/teaching/mp11/mp11-10.pdf)
    - [[mathematical programming]] Chapter 10 [[network planning]] [[least-cost current]] problem and [[negative closure removal]] method

---
This page is auto-translated from [/nishio/最小費用流は線形計画問題](https://scrapbox.io/nishio/最小費用流は線形計画問題) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
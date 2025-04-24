---
title: "Shortest path dual and differential constraints"
---

- Why [[differential constraint]] appears in [[LP twins]] of [[shortest route]] problem?
![image](https://gyazo.com/6383c2b4450a186f5a729b809b359e18/thumb/1000)
- The shortest path problem corresponds to the special case of the [[least-cost current]] problem, where there is enough capacity on the edges to flow 1
- A distinction must be made between having no edges and having edges and zero cost.
    - Creating variables to express the presence or absence of edges gets complicated.
    - and assume that the edge sets are prearranged in a row and mapped to the natural numbers.
- Consider a $|E| \times |V|$ matrix A that expresses which vertices each edge connects
    - Row i is for edge $i = (u, v)$ with column u = -1, column v = 1
- Consider a $|V|$-dimensional vector b representing a starting point and an end point
    - Starting point s is -1, ending point t is 1
- Let f: flow, c: cost be a $|E|$ dimensional vector
- This way it can be written simply as [linear programming problem
    - minimize: $f^T c$
    - subject to:
        - $A^Tf = b$
        - $f \ge 0$
    - The [[dual linear programming problem]] can be written using the $|V|$-dimensional vector p (potential) as
    - maximize: $p^T b$
    - subject to:
        - $Ap \le c$
- Row i of A is in the form of a difference if we recall that u column = -1, v column = 1 for edge $i = (u, v)$, b is -1 for starting point s and 1 for ending point t
    - maximize: $p_t - p_s$
    - subject to:
        - $p_v - p_u \le c_e \quad (\mathrm{for\,all\,} e = (u, v))$

reference data
    - [[duality]]
    - [[LP, Graphs and Formulations]]
- Both are formulated using the set of edges $\delta^+(v), \delta^-(v)$ entering and leaving a point, but how that corresponds to the general form of the linear programming problem expressed in terms of matrix multiplication and how it is dual was not obvious to me so I bit the bullet.

---
This page is auto-translated from [/nishio/最短経路の双対と差分制約](https://scrapbox.io/nishio/最短経路の双対と差分制約) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
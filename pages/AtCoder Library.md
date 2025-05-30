---
title: "AtCoder Library"
---

> Various algorithms implemented on the [[AtCoder]] side
- [https://atcoder.jp/posts/517](https://atcoder.jp/posts/517)

[[AtCoder Library Practice Contest]]
- Commentary AC'd all the way through the practice contest.

Anyway, I checked and about 1/3 to 1/2 of it was already implemented. I'll put it in the same directory structure as the ACLs and license it under the MIT license later.
The rest of the unimplemented ones will be implemented as soon as possible, since the officials say "this is a frequently used algorithm".

> I'd like to see a Python implementation of the AtCoder Library, which is already full of ordinary algorithms (≈ just take it from yosupo judge or AOJ), and make it faster by using numpy/scipy/networkx or cython or something like that. I'd like to see something like this [src](https://twitter.com/n_knuu6/status/1303026130279047168)
- I'm thinking that the All Submit time order ranking in the Practice Contest will be the place to compete for library speed.
- I used to be into speeding things up with [[Numba]] and [[Cython]], but recently I've come full circle and am interested in speeding things up with PyPy without sacrificing flexibility.

Contents
    - [[Fennic tree]]
    - A tree structure (also called a Binary Indexed Tree) that can efficiently both compute partial sums and update elements
    - [B: 600ms](https://atcoder.jp/contests/practice2/submissions/16567562) PyPy provisional first place
    - [[segment tree]] [J - Segment Tree](https://atcoder.jp/contests/practice2/tasks/practice2_j) [454 ms [https://atcoder.jp/contests/practice2/](https://atcoder.jp/contests/practice2/) submissions/16567936]PyPy Tentative #1 [K - Range Affine Range Sum](https://atcoder.jp/contests/practice2/tasks/practice2_k)
    - The tree can be O(logN) summed or minimized when a fixed number of elements are updated by random access.
    - [[Delayed propagation segment tree]]  [L - Lazy Segment Tree](https://atcoder.jp/contests/practice2/tasks/practice2_l)
- String Algorithm Assortment
        - [[suffix array]]
    - [[LCP array]] [I - Number of Substrings](https://atcoder.jp/contests/practice2/tasks/practice2_i)
        - [752ms](https://atcoder.jp/contests/practice2/submissions/16567345) PyPy provisional first place
    - z_algorithm
- Math Algorithm Assortment
    - pow_mod
    - inv_mod
            - [[Power, inverse, factorial, factorial inverse, and combination in Python]] implemented in
    - crt
            - [[Chinese remainder theorem]]
    - [[floor_sum]]
        - [C - Floor Sum](https://atcoder.jp/contests/practice2/tasks/practice2_c)
- Convolution [F - Convolution](https://atcoder.jp/contests/practice2/tasks/practice2_f)
    - In Python, the equivalent of [[np.convolve]] or something like that.
    - [[Two Snuke]] couldn't fit on the int64, so I did it myself.
- Modint Structure that automatically takes mod
    - In Python, it would look pretty if you could achieve this with operator overloading, but I think the situations where this would be used are situations where you can't afford the overhead of a function call.
        - Looks like a good strategy using [[fast long integers]].
- graph
    - [[DSU]]
        - For an undirected graph, add edges, determine whether vertices are connected, and then process in O(α(n)) time.
        - You mean [[UnionFind]]?
        - [A: 277ms](https://atcoder.jp/contests/practice2/submissions/16567503) PyPy provisional first place
    - Maxflow  [[maximum flow]]  [D - Maxflow](https://atcoder.jp/contests/practice2/tasks/practice2_d)
    - MinCostFlow  [[least-cost current]]  [E - MinCostFlow](https://atcoder.jp/contests/practice2/tasks/practice2_e)
    - [[SCC]] [G - SCC](https://atcoder.jp/contests/practice2/tasks/practice2_g)
        - Strongly connected component decomposition of directed graphs
    - [[2-SAT]] [H - Two SAT](https://atcoder.jp/contests/practice2/tasks/practice2_h)
        - Determine if there exists an assignment that satisfies the logical expression of the form $\bigvee (x_{i0} = v_{i0} \wedge x_{i1} = v_{i1})$, and if so, obtain one of these assignments

You can practice here.
- [https://atcoder.jp/contests/practice2](https://atcoder.jp/contests/practice2)
Python Related Articles
- [AtCoder Library Practice Contest Entry (Python) - Qiita](https://qiita.com/c-yan/items/46845ba9deea43930544)

---
This page is auto-translated from [/nishio/AtCoder Library](https://scrapbox.io/nishio/AtCoder Library) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
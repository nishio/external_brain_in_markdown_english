---
title: "Dinic"
---

    - Algorithm for finding [maximum flow
    - Dinic is O(V^2E)
    - [[History of Algorithms for Maximum Flow]]
- [AOJ GRL_6_A Maximum Flow](http://judge.u-aizu.ac.jp/onlinejudge/description.jsp?id=GRL_6_A&lang=jp) to verify implementation.
- My Python implementation (verified by AOJ)
    - The edge is waiting in defaultdict(dict), so there is no need to have the index of the inverse side to get the inverse side.
        - (Many C++ implementations have an inverse index on each side.)
    - Do not search for previously explored edges.
        - This is achieved by having "the first index of the edge not yet explored" in the `itertion_count`.
        - To use this, we need a mapping from index to edges, so we make it first in `max_flow`: `edges_index`.
- [GitHub](https://github.com/nishio/atcoder/blob/master/libs/dinic_maxflow.py)


Implementation of others
    - [[anthology]] 　p.194
- [http://algoogle.hadrori.jp/algorithm/dinic.html](http://algoogle.hadrori.jp/algorithm/dinic.html)
- [https://ei1333.github.io/luzhiled/snippets/graph/dinic.html](https://ei1333.github.io/luzhiled/snippets/graph/dinic.html)
- [https://tubo28.me/compprog/algorithm/dinic/](https://tubo28.me/compprog/algorithm/dinic/)
- [http://www.prefield.com/algorithm/graph/dinic.html](http://www.prefield.com/algorithm/graph/dinic.html)


- [[Maximum two-part matching]]

---
This page is auto-translated from [/nishio/Dinic](https://scrapbox.io/nishio/Dinic) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
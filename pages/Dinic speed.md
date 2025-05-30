---
title: "Dinic speed"
---

The computational complexity of [[Dinic]] is O(V^2E), and when E is proportional to V, V=10000, it seems that it cannot be solved, but it is considered "faster in reality", and in fact it is fast, then how fast is it?

- [Dinic method and its time complexity - Misawamemo](https://misawa.github.io/others/flow/dinic_time_complexity.html)
    - Computational complexity is reduced under some conditions when the side capacity is an integer.
        - When maximum flow is F $O(FE)$.
        - When the capacity of an edge is at most C $O(C E^{3/2})$.
            - and no multiple edges $O(CV^{2/3}E)$.
        - When the flow through each vertex is at most F $O(FV^{1/2}E)$.
            - Solving bipartite matching with maximum flow corresponds to the case F=1 above
    - For implementations using dynamic trees, for general graphs $O(VE\log V)$.
    - [On the maximum flow problem. - Practice Book. - TopCoder Department](https://topcoder-g-hatena-ne-jp.jag-icpc.org/Mi_Sawa/20140311/)
    - [On the Maximum Flow Problem, Part 3 - Practice Chos. - TopCoder Department](https://topcoder-g-hatena-ne-jp.jag-icpc.org/Mi_Sawa/20140320.html)

- If the edge capacity is constant $O(\min \{ E^{1/2}, V^{2/3} \} E)$ [PDF](https://www.cs.bgu.ac.il/~dinitz/Papers/Dinitz_alg.pdf)


---
This page is auto-translated from [/nishio/Dinicの速さ](https://scrapbox.io/nishio/Dinicの速さ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
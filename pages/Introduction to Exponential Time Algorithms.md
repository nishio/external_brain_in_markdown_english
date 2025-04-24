---
title: "Introduction to Exponential Time Algorithms"
---

![image](https://gyazo.com/977ede9fb56afe8240c8f2b43c72179e/thumb/1000)
[https://www.slideshare.net/wata_orz/ss-12131479](https://www.slideshare.net/wata_orz/ss-12131479)
- Introduction to [[exponential-time algorithm]] [[Yoichi Iwata]].

- What index?
        - [[TSP]]  $e^{n\log n}→2^n$
        - [[Maximum Creek Problem]]  $2^V V → 2^{\sqrt{2E}} V$
    - The graph "[[range (e.g., of voice)]]"
            - [[grid graph]] [[pathwidth]] is small
- What is the bottom of the index?
        - [[half-full enumeration]]  $2^n→2^{n/2}$
        - [[maximal independent set problem]]  $2^n n → 1.466^n n$
    - Search algorithm 23
    - [[FPT Algorithm]]
    - Exponential time algorithm only with respect to parameter 𝑘 independent of input size
        - [[minimum vertex coverage problem]]  $n^{k+1} → 2^kn$
            - [[bounded search tree]]
    - kernel
        - The method of pre-processing a polynomial time O(kn) to reduce the problem size to less than or equal to a function 𝑓(𝑘) of 𝑘 is called [[carnellise]], and the reduced problem is called the kernel
        - [[Steiner tree problem]]  $3^kn2^km$
    - [[principle of inclusion]]
        - [[Hamilton Pass]] in polynomial space.
        - [[graph-coloring problem]]   [[number of colors]] $k^n→3^n→2^nn$
        - [[fast zeta transformation]]
        - [[folding backwards body drop]]
        - $(f\cdot g)(S) = \sum_{T \subseteq S} f(T) g(S \backslash T)$
        - Faster DP for sets $3^𝑛 → 2^n$.
        - [[Number of complete matches]] The number of [[perfect matching]] can be $O(2^{n/2}$.
- [[Color Coding]]
    - [[k-Cycle]] Determine if the graph contains a simple closed path of length 𝑘 $n^k → (2e)^km$.
- [[Bandwidth]] Arrange vertices in a row and minimize the length of the longest edge $n!→5^𝑛$.
- [[Cut & Count]] Steiner tree problem on a grid graph c^w
- [[Iterative Compression]] Determine if a tree can be formed by removing 𝑘 points from a graph 3^k

---
This page is auto-translated from [/nishio/指数時間アルゴリズム入門](https://scrapbox.io/nishio/指数時間アルゴリズム入門) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
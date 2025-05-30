---
title: "codefestival_2016_final_C"
---

[C - Interpretation](https://atcoder.jp/contests/cf16-final/tasks/codefestival_2016_final_c)
![image](https://gyazo.com/ba263384ca6d2220146d053b4cf027c8/thumb/1000)
- Thoughts.
    - The question is to determine whether the graph is connected when "there is a common language" is an edge with a person as a vertex.
    - Since there are 10^5 people, determining whether or not an edge exists for a pair of people would be 10^10, so it can't be done naively.
    - It seems important that the total number of Ki is capped at 100,000.
        - The naive thing is that NM adds a strong constraint where it's 10^10.
        - I thought you meant that it's OK to process linear orders for this.
        - Create a "language -> set of people who speak that language." Linear Order
        - The people in this set are consolidated
            - Put into [[UnionFind]], O(n log n)
        - Finally, we can check if everyone's root is the same, O(n log n)
- Official Explanation
    - The principle is the same, but the arrangement is "language is also included in the vertex and interpreted as a bipartite graph".
            - [[Bipartite graph with edges as vertices]]
    - The graph increases to N+M vertices, but the number of edges is reduced to 10^5, so UnionFind is sufficient.

---
This page is auto-translated from [/nishio/codefestival_2016_final_C](https://scrapbox.io/nishio/codefestival_2016_final_C) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
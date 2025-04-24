---
title: "Bipartite graph with edges as vertices"
---

- A graph can be a bipartite graph with edges (and similar vertex-to-vertex relationships) as vertices
    - That's still fine in terms of finding a connected component.
- ![image](https://gyazo.com/c7b9a05ea68b75db5e9f55b7f68cf36a/thumb/1000)
- This conversion is beneficial when it is expensive to build an edge in Yang
    - For example, "an edge is subtracted when a vertex has a sequence of length m and the two vertices have a number in common."
        - It costs O(V^2M).
        - O(VM) when the number is also a vertex.
        - The number of vertices increases, but it is not important because UnionFind is almost of constant order
        - It is not generally true that the number of edges is reduced
            - The case with fewer constraints [[codefestival_2016_final_c]].

- [[problem transformation]]

---
This page is auto-translated from [/nishio/辺を頂点にして二部グラフ](https://scrapbox.io/nishio/辺を頂点にして二部グラフ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
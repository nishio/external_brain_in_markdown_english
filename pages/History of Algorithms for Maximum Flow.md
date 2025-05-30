---
title: "History of Algorithms for Maximum Flow"
---

from [[Dinic]]
History of Algorithms for Maximum Flow
- [Ford-Fulkerson algorithm - Wikipedia [https://ja.wikipedia.org/wiki/%E3%83%95%E3%82%A9%E3%83%BC%E3%83%89%E3%83%BB%E3%83%95%E3%82%A1%E3%83%](https://ja.wikipedia.org/wiki/%E3%83%95%E3%82%A9%E3%83%BC%E3%83%89%E3%83%BB%E3%83%95%E3%82%A1%E3%83%) AB%E3%82%AB%E3%83%BC%E3%82%BD%E3%83%B3%E3%81%AE%E3%82%A2%E3%83%AB%E3%82%B4%E3%83%AA%E3%82%BA%E3%83%A0]
    - 1956
    - May not stop if capacity is an unreasonable number
    - If the capacity is an integer, O(Ef) with the maximum flow as f
        - This is due to the increase in flow at each step.
        - For rational numbers, multiply by an appropriate integer to get an integer.
- [Edmonds Karp's algorithm - Wikipedia [https://ja.wikipedia.org/wiki/%E3%82%A8%E3%83%89%E3%83%A2%E3%83%B3%E3%82%BA%E3%83%BB%E3%82%AB%E3%83%BC%](https://ja.wikipedia.org/wiki/%E3%82%A8%E3%83%89%E3%83%A2%E3%83%B3%E3%82%BA%E3%83%BB%E3%82%AB%E3%83%BC%) E3%83%97%E3%81%AE%E3%82%A2%E3%83%AB%E3%82%B4%E3%83%AA%E3%82%BA%E3%83%A0]
    - 1972
    - O(VE^2)
        - Almost identical to Ford Fulkerson's algorithm.
        - From the start, first do a width-first search to find the distance.
            - Search only in the direction away from the start when searching for increasing paths.
        - [Edmonds–Karp algorithm - Wikipedia](https://en.wikipedia.org/wiki/Edmonds%E2%80%93Karp_algorithm)
- [Dinic's algorithm - Wikipedia](https://en.wikipedia.org/wiki/Dinic%27s_algorithm)
    - 1970
    - O(V^2E)
    - Almost identical to Edmonds-Karp's algorithm.
        - There are additional innovations.
        - And it can even be O(VElogV).
---
This page is auto-translated from [/nishio/最大流を求めるアルゴリズムの歴史](https://scrapbox.io/nishio/最大流を求めるアルゴリズムの歴史) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
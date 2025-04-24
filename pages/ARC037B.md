---
title: "ARC037B"
---

[B - Baum Test](https://atcoder.jp/contests/arc037/tasks/arc037_b)
- ![image](https://gyazo.com/ee65e33af57b50b7a728b664b743d615/thumb/1000)
- Thoughts.
    - If the number of edges is the number of vertices - 1 for the connected component, then tree
    - Since the total number of edges is known, is it sufficient to find and calculate the number of connected components? →This is wrong.
        - There could be a connected component that has multiple extra edges.
    - Since there are at most 5050 edges, there is plenty of room to find the connected components and then count the number of edges for each connected component.
        - For each edge, one vertex belongs to
- Official Explanation
        - [[Find the connected components with DFS]]
    - If there are already visited vertices other than the direction you came from, there is a closed road.

---
This page is auto-translated from [/nishio/ARC037B](https://scrapbox.io/nishio/ARC037B) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "nomura2020C"
---

[C - Folia](https://atcoder.jp/contests/nomura2020/tasks/nomura2020_c)
- ![image](https://gyazo.com/7f80f1a1ef30beceaa1abc2ff094f93c/thumb/1000)
- Thoughts.
    - Not only is it possible, but it's a lot of work to maximize the vertices...
    - When does the number of vertices increase?
    - Should we try to make it as scanty as possible?
    - Huh? Same thing, huh?
        - ![image](https://gyazo.com/0c74cabd6084255d9b2a3449d48767c6/thumb/1000)
    - It is not uniquely determined by...
    - Start with 1, subtract A0 and multiply by 2, which is the number of vertices at the next height, then subtract A1, which is the leaves, and multiply by 2, which is the number of vertices at the next height.
    - If this is just 0 at the end, it is feasible
    - The number of vertices is unique since it is obtained above.
- Official Explanation
    - Ah, I see, "the number of children is less than or equal to 2", so there can be a vertex with one child.
        - Problem condition misunderstanding. Think again.
- A new thought.
    - In other words, it's times like these that make the difference.
    - ![image](https://gyazo.com/ba00c9de4d2861b76f5a1520806c4abe/thumb/1000)

    - If the vertex at the top height is x, then we can put at most 2x vertices at the current height
    - Ai of them are used as leaves.
    - You can't have all 2x-Ai vertices.
        - Without the apex of the child, it would be a leaf.
        - If we hang the vertices of the children as unbundled as possible, we can create vertices up to the sum of the number of children.
    - Do the smaller of the two values.
- Official Explanation
    - It proves optimal to place as many vertices as possible in the above way


---
This page is auto-translated from [/nishio/nomura2020C](https://scrapbox.io/nishio/nomura2020C) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
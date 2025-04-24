---
title: "ACLPC E"
---

![image](https://gyazo.com/eaaba4778f81bf4f4751b1e923ffae74/thumb/1000)



from [[AtCoder Library Practice Contest]]
ACLPC_E
[E - MinCostFlow](https://atcoder.jp/contests/practice2/tasks/practice2_e)
- ![image](https://gyazo.com/4a918321865b3d3cb12a58f05b197d54/thumb/1000)
    - [[least-cost current]]
    - [Minimal Cost Flow (Primal-Dual) | Luzhiled's memo](https://ei1333.github.io/luzhiled/snippets/graph/primal-dual.html)
- In Flow's words, "less than K chosen" means "K edges of capacity are connected."
- The squares to be chosen are kept on the sides with capacity 1, and the side with the flow when the minimum cost flow is found is the "chosen square".
- We can make sure that the options that gain X when you choose them cost you a large value INF when you don't choose them, and cost you INF-X when you do choose them.
    - ![image](https://gyazo.com/5a9d6fb8d110d875509cebc706ad10e7/thumb/1000)![image](https://gyazo.com/025a8b01a2bac694b9a720de4339d0d1/thumb/1000)
    - ![image](https://gyazo.com/eaaba4778f81bf4f4751b1e923ffae74/thumb/1000)


---
This page is auto-translated from [/nishio/ACLPC E](https://scrapbox.io/nishio/ACLPC E) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
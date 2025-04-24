---
title: "ACLPC G"
---

from [[AtCoder Library Practice Contest]]
ACLPC_G
[G - SCC](https://atcoder.jp/contests/practice2/tasks/practice2_g)
- ![image](https://gyazo.com/3f039350389b2300aa35f5bf74deb838/thumb/1000)
    - [[strongly-coupled component]] decompose
    - [Strongly connected component - Wikipedia](https://en.wikipedia.org/wiki/Strongly_connected_component)
    - [Semantics and Algorithms of Strongly Connected Component Decomposition | The Beautiful Story of High School Mathematics](https://mathtrain.jp/kyorenketsu)
    - [ei1333's page](https://ei1333.github.io/algorithm/strongly-connected-components.html) C++
- Search depth-first and number in order of return.
- Reverse the edges and perform depth-first search again in the order of the previous number. The traced range is the strongly connected component
---
This page is auto-translated from [/nishio/ACLPC G](https://scrapbox.io/nishio/ACLPC G) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
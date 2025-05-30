---
title: "TTPC2015L"
---

[L - graph coloring](https://atcoder.jp/contests/ttpc2015/tasks/ttpc2015_l)
![image](https://gyazo.com/fdaa6debdfe439cb7fd207ada2b49c45/thumb/1000)

Thoughts.
- Known to be a minimum cut related problem, but unclear if the theme is just minimum cut = maximum flow or if the solution is also minimum cut
- The maximum flow when all the blue edges are removed is just a constant, so we can find it first, denoted by the constant F below
- A problem of choosing between "erase or not erase" for the blue edge of a given graph, and setting the maximum flow to F.
    - Since the blue side is 200, 2^200 is impossible, so solving with the smallest cut seems like a good idea?
    - How do we express the constraint that "the maximum flow is F?"
    - Would the answer be to add the edges under the condition of "no increase in maximum flow" from the maximum flow paint-out with all the blue edges removed?
        - I have a feeling that's not quite true, but let's consider it for once.
    - ![image](https://gyazo.com/6bab8fe1daa758f42c2371e691b03d0a/thumb/1000)
        - Side D increases the maximum flow because S and T are connected when selected
            - Should be cut at a cost of 1
            - The two infinity sides are redundantly written, and it doesn't matter if you shrink one or the other, but we'll do that later.
        - Edge C connects S and A when selected
            - But A doesn't need to be cut because it doesn't matter if it's S
        - The same can be said for the edges connected to E and F.
            - In this case, one of them should be cut.
    - Unconsciously thinking in terms of the "cutting" metaphor led to a useless design, start over.
        - The choice to leave an edge or not in the left graph corresponds to whether to paint the vertex red in the right graph
        - When erasing an edge, pay 1 cost.
        - ![image](https://gyazo.com/40d6397ff6a11ab738e5996b87257dfd/thumb/1000)
        - Oh, this is [[Bipartite graph with edges as vertices]].
    - Is this what you want to do?
- Commentary by others
    - [https://kimiyuki.net/writeup/algo/atcoder/ttpc-2015-l/](https://kimiyuki.net/writeup/algo/atcoder/ttpc-2015-l/)
    - [https://kmjp.hatenablog.jp/entry/2015/09/24/0930](https://kmjp.hatenablog.jp/entry/2015/09/24/0930)

---
This page is auto-translated from [/nishio/TTPC2015L](https://scrapbox.io/nishio/TTPC2015L) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
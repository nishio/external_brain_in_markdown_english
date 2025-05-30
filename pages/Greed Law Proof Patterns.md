---
title: "Greed Law Proof Patterns"
---

    - [[No loss on the exchange.]]
        - [[Replacement does not make it worse.]]
    - Greedy method of selecting in a certain order
    - Show that replacing the slower order with the faster order does not decrease the score you want to maximize
    - [https://penguinshunya.hatenablog.com/entry/2020/01/21/093846](https://penguinshunya.hatenablog.com/entry/2020/01/21/093846)

- [https://mobile.twitter.com/maspy_stars/status/1198626710599528454](https://mobile.twitter.com/maspy_stars/status/1198626710599528454)
    - > Show advancedness. Indicates the best method at a given "point in time" in "chronological" order.
    - >  Imposing properties that can be assumed for the optimal solution (this form etc. since it is not worse if we replace two of them), we show that it is greedy.
    - [https://maspypy.com/atcoder-参加感想-2020-04-13abc-163](https://maspypy.com/atcoder-参加感想-2020-04-13abc-163)

- [https://mobile.twitter.com/onakasuita_py/status/1250014171149692930](https://mobile.twitter.com/onakasuita_py/status/1250014171149692930)
    - > ・Selection that can be optimal for each operation (meaning that there exists an optimal solution that includes that selection).
    - >  ・After each operation, it can be attributed to a smaller-scale problem, and the solution can be obtained recursively.
    - >  ・The proof is basically a backward reasoning, assuming that all optimal solutions do not include "selection by greed" and showing a contradiction.
        - > ex.)Interval scheduling
        - >  Show at time 0. Let I=`[L,R]` be one of the ones with the smallest R, and assume that all optimal solutions do not contain I. If we take one of the optimal solutions (it is clear that there is an optimal solution) and let J=`[L',R']` be the one with the smallest R, J is contradicted by the fact that J is always replaced by I. Therefore, I may be adopted.
        - > In this way, the phrase "no loss" that we often see in proof of greed does not appear.

- First, show the lower boundary
    - Showing agreement with the lower boundary
    - Therefore, it is the optimal solution
    - [[ARC111]]

- [Requirements for solving coin problems using the greedy method - Qiita](https://qiita.com/s417-lama/items/0cdd95fddb2067876896)

- [https://kimiyuki.net/blog/2017/12/03/matroid-greedy-proof/](https://kimiyuki.net/blog/2017/12/03/matroid-greedy-proof/)

- [[greedy algorithm]]

---
This page is auto-translated from [/nishio/貪欲法の証明パターン](https://scrapbox.io/nishio/貪欲法の証明パターン) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
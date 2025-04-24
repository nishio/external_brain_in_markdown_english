---
title: "Loop detection instead of doubling"
---

- [[doubling]] and not [[loop detection]].
I've paged through two problems that were straightforward to solve with loop detection and mistakenly thought "this is doubling".

- When reading N vertices ahead in a graph with V vertices
        - [[doubling]]
        - O(VlogN) pre-processing allows O(logN) for this process
        - Gain if this process is repeated more than V times.
        - If logN is too large, even this is not possible.
        - [[loop detection]]
        - If it has a single starting point, it can be pre-processed with O(V) in the worst case.
            - What should we do at an arbitrary starting point? If we do it naively, O(V^2)
        - If N is large enough to enter the loop, subtract the distance to enter the loop and take the remainder by the loop length
        - O(1)
- Comparison
    - If N is high V at any starting point, doubling is lighter preprocessing.
    - Loop detection is more advantageous for a single starting point
    - Loop detection if N is excessively large at any starting point

---
This page is auto-translated from [/nishio/ダブリングではなくループ検出](https://scrapbox.io/nishio/ダブリングではなくループ検出) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
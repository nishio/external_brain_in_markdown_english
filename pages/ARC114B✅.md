---
title: "ARC114B✅"
---

from [[ARC114]]
ARC114B✅
- Thoughts.
    - When merging, upstream cannot be selected at the same time.
    - If you choose upstream, you must also choose downstream.
    - SAT-like
        - But it's a matter of counting up instead of building one, so it's not.
        - [[strongly-coupled component decomposition]].
        - Isolated loops are "choose all" or "don't choose all".
        - Where's the rest?
            - DAG…
            - No, it's not a DAG, there's only one edge from one vertex, so there's no branching.
        - Isolated loops and trees flowing into loops
            - How to calculate the tree part...
        - No, I thought you couldn't choose the tree part in the first place.
            - Confluence occurs at the point of flow into the loop, but condition 2 cannot be met.
        - Eventually, the number of loops is 2^N-1 with N as the number of loops.
- Official Explanation
    - The number of loops and the number of connected components match

---
This page is auto-translated from [/nishio/ARC114B✅](https://scrapbox.io/nishio/ARC114B✅) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
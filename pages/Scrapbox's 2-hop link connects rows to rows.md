---
title: "Scrapbox's 2-hop link connects rows to rows"
---

from  [[Diary 2023-12-06]]
Scrapbox's [[2-hop link]] is a line-to-line link
![image](https://gyazo.com/b82ce4d167c97b4bcb9522a5131dab88/thumb/1000)

- In the context of vector embedding in [[vector search]], not only embedding of the document itself, but also embedding of finer units and having [[adjacency]] and [[parent-child]] relationships among them are being done.
- For example, [[Sentence-aware Contrastive Learning for Open-Domain Passage Retrieval]].

When viewed from this perspective
- Scrapbox has a three-level structure of "page, row, link".
- 2-hop links are links where "line A" and "line B" are connected by "having a common link".
can be said to be

In a non-linked document, something similar can be achieved by embedding each substructure, for example, a line or a sentence.
![image](https://gyazo.com/3a3bd18b0c45c656b71eec663c38601b/thumb/1000)
- Find the nearest non-identical document line from each line.
        - Can achieve the "effect of being able to discover documents that mention common things" as described in [Scrapbox reminds me of what I've forgotten.
- The Scrapbox link can be interpreted as a human [[bracketing]] that achieves it with high speed and high quality.

---
This page is auto-translated from [/nishio/Scrapboxの2ホップリンクは行と行をつなぐリンク](https://scrapbox.io/nishio/Scrapboxの2ホップリンクは行と行をつなぐリンク) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
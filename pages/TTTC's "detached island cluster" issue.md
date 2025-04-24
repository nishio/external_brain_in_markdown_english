---
title: 'TTTC''s "detached island cluster" issue'
---

![image](https://gyazo.com/7f498e63c2d20ba6a814393d20be2baa/thumb/1000)
A discussion of the phenomenon of strange clusters in places that fly like this in [[Talk to the City]].

Observation Fact: There have been a number of duplicate examples given by fewshot to the outlying island clusters.
![image](https://gyazo.com/3d86c6eabef670dd9dde2feae56594e2/thumb/1000)

Guess:.
- Sometimes returns examples of fewshot instead of `[]` for input data that cannot be successfully opinion-extracted
- Maybe [[UMAP]] behaves as "there are clusters with high density" when many data points with almost the same content overlap.
    - I think the resulting increase in spatial resolution of the surrounding area gives the appearance of these remote islets.

Countermeasures:.
- If you show it to users as it is, most users will react, "What is this remote islet?" and will be the first to see it.
- Separate islets are "opinion data incorrectly extracted due to inadequate instructions to LLMs" and should be removed as a visualization of opinion.
- The data is the effect of "data that does not extract opinions well," so we will add a newshot to deal with that data.
    - Specifically, click on a point in this cluster to check the input data to the LLM, and if there is no opinion to be extracted, `[]`, otherwise, add that opinion as a reply in the prompt fewshot and start over from the extraction phase
    - You don't have to do the whole cluster, just add one or two cases as a realization to get rid of it.
        - Maybe adding `[]` to the fewshot moves the boundary of "to `[]` or not".

As an aside, it would be better to UNIQUE it right after EXTRACTION in the first place...

---
This page is auto-translated from [/nishio/TTTCの「離れ小島クラスタ」問題](https://scrapbox.io/nishio/TTTCの「離れ小島クラスタ」問題) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
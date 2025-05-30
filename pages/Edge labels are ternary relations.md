---
title: "Edge labels are ternary relations"
---

- [[edge label]] is [[triadic relation]].
![image](https://gyazo.com/5c28ac99bc6dd6baacbf1bb005f3959b/thumb/1000)

There are cases where you want to assign a symbol to a relation, but if you make the kozane stick to the edge, a circular reference to "the way the line is drawn depends on the position of the kozane" and "the position of the kozane depends on the way the line is drawn" occurs, which is not bad, but I thought it was subtle.

Since the relation is not a binary relation in the first place, but a general polynomial relation, it would be enough if the relation were attached to a binary relation.

What does "good enough" mean?
- It can serve the purpose of "not losing information when it is moved."

Edge labels = labels attached to edges, displaying the relationship between "edges" and "labels" by proximity
- When you move an endpoint of an edge, the edge also moves -> the label must also move in order for the "display of relations by proximity" not to be broken.
- But since the edge was introduced because "we want to make sure that we can move it freely and not break the relationship," the same principle should apply here.

What the input UI should be is a difficult question.
- Especially the ternary relationship labeled one-way arrows, all three legs being different.

---
This page is auto-translated from [/nishio/辺ラベルは三項関係](https://scrapbox.io/nishio/辺ラベルは三項関係) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
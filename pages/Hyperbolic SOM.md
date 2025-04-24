---
title: "Hyperbolic SOM"
---

[[Hyperbolic Self-Organizing Maps for Semantic Navigation]]
[Hyperbolic Self-Organizing Maps for Semantic Navigation](https://papers.nips.cc/paper_files/paper/2001/hash/093b60fd0557804c8ba0cbf1453da22f-Abstract.html)
<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
The above paper (by Ontrup et al.) proposes a Hyperbolic SOM for navigating to the "[[semantic space]]" of a document set. At the time, it was mainly applied to [[text mining]] and [[categorization]], and emphasized the natural mapping and visualization of hierarchical structures ("[[fisheye-like]]" magnification by hyperbolic space) compared to [[SOM]] on [[Euclidean space]]. It performs as well as or better than standard SOM in quantization error and cluster purity, and also facilitates novel topic detection and understanding of inter-document similarities.

Modern UMAP and t-SNE are fast and capture the structure of high-dimensional data well locally, but do not necessarily handle hierarchical or tree-like structures explicitly. Hyperbolic SOM, on the other hand, has the unique advantage of being able to map [[hierarchical data]] and [[tree-like data]] more naturally by utilizing the properties of hyperbolic geometric space. Therefore, even in the situation where modern nonlinear dimensionality compression methods dominate, SOM utilizing hyperbolic spaces can still occupy a useful position, especially in tasks that emphasize hierarchical relationships.

---
This page is auto-translated from [/nishio/Hyperbolic SOM](https://scrapbox.io/nishio/Hyperbolic SOM) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
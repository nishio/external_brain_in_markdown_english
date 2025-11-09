---
title: "Embedding Atlas(Apple)"
---

[Overview | Embedding Atlas](https://apple.github.io/embedding-atlas/overview.html)

> [NirantK](https://x.com/NirantK/status/1954081728525742365) [[Apple]] just dropped a killer open-source [[visualization tool for embeddings]] — [[Embedding Atlas]] — and it’s surprisingly powerful for anyone working with large text+metadata datasets.
>  Apple just released Embedding Atlas, a killer open source visualization tool for embedding that is surprisingly powerful for anyone working with large text + metadata datasets.
>
>  This reminds me of [[Nomic]]'s Atlas, but I never got around to using it
>  This reminds me of Nomic's Atlas, but I haven't had time to use it
>
>  We’re talking real-time search, multi-million point rendering, and automatic clustering with labels.
>  We are talking about real-time searches, rendering of millions of points, and automatic clustering by label.
>
>  One of their showcase examples visualizes ~200K wine reviews using embeddings + metadata like price, country, and tasting notes. And it is lightning fast even on my browser! No separate code needed!
>  One of their showcase examples visualizes ~200K wine reviews with embedded + metadata (price, country, tasting notes, etc). And it's super fast in my browser! No separate code required!
>
>  It nails what most LLM devs need but often hack together:
>  This nails what most LLM developers need, but often hack together.
>
>   [[UMAP]] projections
>   Faceted search across metadata (e.g. “country vs. price”)
>   Hover + tooltip on raw points
>   Interactive filters, histograms, and cluster overlays
>   Cross-linked scatterplot + table views
>  UMAP projection method
>  Faceted search across metadata (e.g., "country and price")
>  Hover over raw point + tooltip
>  Interactive filters, histograms, cluster overlays
>  Crossbridge scatterplot + table view
>
>  Under the hood:
>  • Fast rendering using WebGPU (with WebGL fallback)
>  • Embedding-based semantic similarity search
>  • Kernel density contours for spotting clusters or outliers
>  Under the hood:.
>  - Fast rendering using [[WebGPU]] (with [[WebGL]] fallback)
>  - Embedded-based semantic similarity search
>  - Kernel density contours for detecting clusters or outliers
>
>  You just upload your .jsonl or .csv with text + vector + metadata. It handles the rest: clustering, labeling, UI layout, everything.
>  Simply upload a .jsonl or .csv containing text + vectors + metadata. We handle all the rest, including clustering, labeling, UI layout, etc.
>
>  This feels like the LLM-native version of Tableau — but optimized for text, chat and modern data needs
>  This feels like a native LLM version of Tableau, but optimized for your text, chat, and modern data needs
>
>  If you’re building RAG evals, search tuning, clustering explainability, or even dataset audits — this could be your new favorite tool.
>  If you are building RAG evaluations, search tuning, clustering accountability, or even dataset auditing, this could be your new favorite tool.
>  ![image](https://pbs.twimg.com/media/Gx5K-KbbsAIO95H?format=jpg&name=medium#.png) ![image](https://pbs.twimg.com/media/Gx5K-f-akAAUZRM?format=jpg&name=medium#.png)


---
This page is auto-translated from [/nishio/Embedding Atlas(Apple)](https://scrapbox.io/nishio/Embedding Atlas(Apple)) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
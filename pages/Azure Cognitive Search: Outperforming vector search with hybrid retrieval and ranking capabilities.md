---
title: "Azure Cognitive Search: Outperforming vector search with hybrid retrieval and ranking capabilities"
---

![image](https://gyazo.com/8e2fa02e91d9ee1566bd48aeb6008048/thumb/1000)
[https://techcommunity.microsoft.com/t5/azure-ai-services-blog/azure-cognitive-search-outperforming-vector-search-with-hybrid/ba-p/3929167](https://techcommunity.microsoft.com/t5/azure-ai-services-blog/azure-cognitive-search-outperforming-vector-search-with-hybrid/ba-p/3929167)
[[BM25]] + vector neighborhood search in [[Hierarchical Navigable Small World]] ([[HNSW]]) + [[rerank]].

7/18 Public Preview begins
- [Azure Cognitive Search now includes vector search functionality and is in private preview - Qiita](https://qiita.com/nohanaga/items/f710cac82072b63bc73f)
- [Azure Cognitive Search vector search in Python](https://zenn.dev/microsoft/articles/34fdf03208b932)

summary
- [[Azure Cognitive Search]] enhances the search step of [[RAG]] applications that previously used vector search. The platform supports [[vector search]] and introduces additional features to improve relevance. This article discusses the technology behind Azure Cognitive Search, focusing on two main layers: search and ranking. In particular, it highlights the effectiveness of hybrid search combined with semantic ranking in Generative AI applications. It also delves into the importance of document chunking and how semantic ranking prioritizes the best results.
- Three Insights
    - Hybrid Search and Semantic Ranking: Azure Cognitive Search's hybrid search combines both keyword and vector search methods. Combined with semantic ranking, it significantly improves relevance, especially for generative AI applications.
    - Document Chunking Strategy: Chunking documents into passages of limited length is essential for generative AI applications. This ensures that the most relevant parts of the document are ranked first and that the entire document is searchable without being truncated.
    - Semantic Ranking: In Generative AI scenarios, it is important to prioritize the top results, and Azure Cognitive Search's Semantic Ranker uses a transformer model with a cross-attention mechanism to calibrate the It generates ranker scores and displays the best results at the forefront.

> [daiki15036604](https://twitter.com/daiki15036604/status/1703913169511727217/history) Azure Cognitive Search's hybrid + semantic ranking performed better than pure I heard it performed better than vector search!
>
>  Available now with no tuning required!

> [hiro_gamo](https://twitter.com/hiro_gamo/status/1703944092982644958) It may be annoying to push it too much, but I'm glad to hear that the customers I work with are migrating to this "Vector +Keyword Seach combined with Azure's own semantic re-ranking" because it's very popular. I'm happy to see that many of my clients are migrating to "Vector +Keyword Seach combined with Azure's own semantic re-rank" because it's very popular.

- [[search (e.g. for someone using a search engine)]]

---
This page is auto-translated from [/nishio/Azure Cognitive Search: Outperforming vector search with hybrid retrieval and ranking capabilities](https://scrapbox.io/nishio/Azure Cognitive Search: Outperforming vector search with hybrid retrieval and ranking capabilities) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
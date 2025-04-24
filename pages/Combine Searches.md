---
title: "Combine Searches"
---

[AI King - Japan's No.1 Quiz AI Competition and won 3rd place｜PKSHA Delta](https://voice.pkshatech.com/n/n83343d0e00e0) 2023-01-04
- > ![image](https://gyazo.com/763fb9ae8f7e017772460b9ef471e515/thumb/1000)
- Talk about combining searches.
    - I'm combining [[DPR]] and [[BM25]].
        - DPR is, in a crude way, [[vector search]], and BM25 is, in a crude way, "modern TF-IDF.
        - Vector search is weak for low-frequency words (= proper nouns, technical terms and product names), so combine ordinary search
- > BM25: Lexical Match Base
- > [[Dense Passage Retriever]] (DPR)... Dense vector-based using pre-trained models
    - Strong semantic similarity
    - Missing low-frequency words / Significant performance degradation outside the distribution (OOD)
- Very small overlap in search results for both DPR and BM25
- → good points on both sides.

- All teams are [[Retriever-Reader]] type
    - Adopted [[Fusion in Decoder]] as Reader
        - Top 100 items
    - > Surveying papers around information retrieval, we found several studies in this context, and seq-to-seq based ones are more accurate than building classifiers on BERT basis
        - Learned Reranker ([[rerank]])

[[PKSHA]]
[[LLM]]
- [[King of AI]]
[[Quiz AI]]


---
This page is auto-translated from [/nishio/検索を組み合わせる](https://scrapbox.io/nishio/検索を組み合わせる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
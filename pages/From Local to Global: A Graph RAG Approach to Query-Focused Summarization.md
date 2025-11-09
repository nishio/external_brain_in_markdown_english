---
title: "From Local to Global: A Graph RAG Approach to Query-Focused Summarization"
---

[https://arxiv.org/abs/2404.16130](https://arxiv.org/abs/2404.16130)
<img src='https://scrapbox.io/api/pages/nishio-en/GPT5/icon' alt='GPT5.icon' height="19.5"/>[[GraphRAG]] is a "global question" that looks at the entire corpus (e.g., What are the main themes? What are the conflicting viewpoints?) ). Entity-relationship graphs are created in advance, and summaries are generated for each community (cluster). When a question is asked, these are combined in a Map→Reduce synthesis to produce the final answer. ([arXiv](https://arxiv.org/html/2404.16130v2))

What the study did.
- The conventional "vector RAG" is strong in extracting local facts, but weak in summarizing and synthesizing the entire context (sensemaking). Therefore, GraphRAG is proposed. ([arXiv](https://arxiv.org/html/2404.16130v2))
- Pipeline (Figure 1)
    1. document → chunking
    2. extract entities, relations, and (if necessary) claims from each chunk with LLM
    3. build a knowledge graph with them
    4. community partitioning of graphs using [[Leiden method]] etc.
    5. generate a summary for each community (hierarchical bottom-up)
        - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/> [[Bottom-up summary generation]]
    6. partial answers to questions from each community summary (Map) → combined into a whole answer (Reduce). ([arXiv](https://arxiv.org/html/2404.16130v2))
- Entity extraction is performed with multipart prompts. The self-reflection prompt compensates for the problem of increased misses in larger chunks. ([arXiv](https://arxiv.org/html/2404.16130v2))

How we evaluated
- Dataset (assumed to be approximately 1 million tokens in size)
    - Podcast: public transcript of Behind the Tech with Kevin Scott (600 token chunks x 1669, overlap 100).
    - News: news for 2013/9-2023/12 (600 token chunks x 3197, overlap 100). ([arXiv](https://arxiv.org/html/2404.16130v2))
- Condition comparison: 4 levels of GraphRAG (C0-C3), Text Direct Summary (TS), Vector RAG (SS). Generation prompts and context windows are unified. Community detection is Leiden with GRASPologic.([arXiv](https://arxiv.org/html/2404.16130v2))
- The evaluation indicators are relative ratings in LLM-as-a-judge (inclusiveness, diversity, empowerment, and directness as a control). In addition, objective indicators are also used together with the number of factual claims and clusters extracted by Claimify. ([arXiv](https://arxiv.org/html/2404.16130v2))

Main Results
- Global system method (GraphRAG/TS) > Vector RAG
    - Inclusivity win rates: 72-83% for Podcasts, 72-80% for News.
    - Diversity win rates: 75-82% for Podcasts, 62-71% for News.
    - On the other hand, the vector RAG has the highest directness (i.e., short and direct). ([arXiv](https://arxiv.org/html/2404.16130v2))
- Efficiency aspect: Root layer C0 consumes 9-43 times fewer tokens per question (advantageous for iterative search for global understanding). The deeper the hierarchy, the more information, but also the more tokens. ([arXiv](https://arxiv.org/html/2404.16130v2))
- Even in objective measures, the global system is superior to the vector RAG in **number of claims (comprehensiveness) and number of claim clusters (diversity)** (e.g. p<.05). ([arXiv](https://arxiv.org/html/2404.16130v2))

Implementation Tips (from the paper)
- Chunk size: If too large, extraction leakage will increase, so use self-reflection combination to balance. ([arXiv](https://arxiv.org/html/2404.16130v2))
- Use of hierarchy:
    - C0 (top level community summary) = iterative search at very low cost.
    - C2/C3 (lower) = When you want to extend inclusiveness and diversity a bit. ([arXiv](https://arxiv.org/html/2404.16130v2))
- Realistic cost of indexing: 600 token window for GPT-4-turbo as an example, about 281 minutes for podcast vocabulary (VM configuration and API conditions specified). ([arXiv](https://arxiv.org/html/2404.16130v2))
- OSS: Microsoft implementation available; also extensions for LangChain/LlamaIndex/NebulaGraph/Neo4j. ([arXiv](https://arxiv.org/html/2404.16130v2))

Limitations and Future
- Limited to validation with approximately 1 million tokens scale and 2 corpora. Cross-disciplinary generalization and comparison of hallucination rates (e.g. SelfCheckGPT) are future work. ([arXiv](https://arxiv.org/html/2404.16130v2))

When to use GraphRAG (personal opinion)
- Questions that require "overall picture, coverage of issues, and multiple perspectives" (organizing trends, overlooking conflicting views, and extracting major themes).
- Workloads that throw global questions at the same data over and over (low-cost iterations at C0 -> "dig" to lower layers as needed).
If the only purpose is to accurately identify individual facts, a conventional vector RAG is more likely to provide a short and direct answer. ([arXiv](https://arxiv.org/html/2404.16130v2))

---
This page is auto-translated from [/nishio/From Local to Global: A Graph RAG Approach to Query-Focused Summarization](https://scrapbox.io/nishio/From Local to Global: A Graph RAG Approach to Query-Focused Summarization) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
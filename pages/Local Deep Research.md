---
title: "Local Deep Research"
---

2025-08-29
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>What is the best way to do [[deep research]] on local files as of August 2025?

<img src='https://scrapbox.io/api/pages/nishio-en/GPT5/icon' alt='GPT5.icon' height="19.5"/>
Mr. Nishio, in conclusion.

Key Points (as of August 2025)
- Deep Research-like" = planning-level multi-stage inference + summary with sources; OpenAI version is designed to read many sources, plan → collect → summarize → always return a report with citations (recently with visual browser). Locally, the requirements are the same: high precision parsing → hybrid search → reranking → multistage reasoning → exact citation. ([OpenAI](https://openai.com/index/introducing-deep-research/?utm_source=chatgpt.com), [OpenAI Help Center [https://help.openai.com/en/](https://help.openai.com/en/) articles/10500283-deep-research-faq?utm_source=chatgpt.com])

Recommended architecture (best solution for each application)

A. Strong "Exact Citation" specialization for research note/paper type
PaperQA2 (high precision RAG across PDF/text, with paragraph and page sources) + LLM/embedding of your choice
- Automates question -> evidence extraction -> response -> page numbered citation for local PDF groups. Scientific but also effective for general documents. ([GitHub](https://github.com/Future-House/paper-qa?utm_source=chatgpt.com), [arXiv [https://arxiv.org/abs/2409.13740?utm_source=chatgpt](https://arxiv.org/abs/2409.13740?utm_source=chatgpt) .com])
- Usage is `Docs.add(path)`→`query()` tiny API. you can choose OpenAI/llama.cpp/Ollama etc. ([PyPI](https://pypi.org/project/paper-qa/4.4.0/?utm_source=chatgpt.com))
In this case: I want to cross reference papers, plans, and minutes with confirmation.

B. "Structured Search" for a complete picture of the corpus + strong discovery
[[GraphRAG]] (knowledge graph + community summary) + LlamaIndex/LangGraph (agentification)
- Automatic extraction of entity relations from corpus → graphing → local QA; strong for discovery of unknown issues and "bird's eye view". ([Microsoft](https://www.microsoft.com/en-us/research/project/graphrag/?utm_source=chatgpt.com), [[microsoft.github.io https:// microsoft.github.io/graphrag/?utm_source=chatgpt.com]])
- When used in conjunction with LangGraph, the long-term task of plan -> collect -> verify -> report can be turned around while maintaining state. ([langchain-ai.github.io](https://langchain-ai.github.io/langgraph/?utm_source=chatgpt.com))
For: Extracting and mapping issues from large amounts of data, and iterating on research design.

C. Quickly "Question the self-catered knowledge base" with a GUI
AnythingLLM / PrivateGPT / Danswer + local LLM
- Drop PDF/MD/Doc in your own UI -> chat search. On-premise complete configuration is also available. ([garmingo.com](https://garmingo.com/blog/p/self-host-anythingllm?utm_source=chatgpt.com), [GitHub [https://github.com/zylon-ai/private](https://github.com/zylon-ai/private) -gpt?utm_source=chatgpt.com], [zenml.io [https://www.zenml.io/llmops-database/scaling-enterprise-rag-with-advanced-vector-search-](https://www.zenml.io/llmops-database/scaling-enterprise-rag-with-advanced-vector-search-) migration?utm_source=chatgpt.com])
When: You want to try it out with minimal construction cost and distribute it to your team.

Common "best" recipe (nominated purchase of parts)
1. parse (PDF/Office)
- Layout-preserving Docling (IBM) or Marker (strong for formulas and tables) + Unstructured (element-labeled partitioning) depending on use. ([IBM Research](https://research.ibm.com/blog/docling-generative-AI?utm_source=chatgpt.com), [GitHub [https://github.com/datalab-to/](https://github.com/datalab-to/) marker?utm_source=chatgpt.com], [Unstructured](https://unstructured.io/blog/how-to-parse-a-pdf-part-1?utm_source=chatgpt.com))
2. indexing (hybrid)
- BM25 (SQLite-vec or Tantivy-type) + embedded two-tier; `sqlite-vec` is lightweight for SQLite operation. ([GitHub](https://github.com/asg017/sqlite-vec?utm_source=chatgpt.com))
- Vector DB is Qdrant (solid) or LanceDB (column-oriented, same format, data and vector cohabitation). ([qdrant.tech](https://qdrant.tech/?utm_source=chatgpt.com), [https://lancedb.com/?utm_source=chatgpt.com](https://lancedb.com/))
3. embedding (Japanese + English)
- Commercial: Voyage-3/4 systems report strong 2025 ratings. ([datastax.com](https://www.datastax.com/blog/best-embedding-models-information-retrieval-2025?utm_source=chatgpt.com))
- OSS Focus: Jina-embeddings-v3 performs well in multilingual MTEB. ([jina.ai](https://jina.ai/news/jina-embeddings-v3-a-frontier-multilingual-embedding-model/?utm_source=chatgpt.com))
(*Final selection is based on own data and evaluated by RAGAS/TruLens, etc.) ([docs.ragas.io [https://docs.ragas.io/en/stable/concepts/metrics/available_metrics/faithfulness/?](https://docs.ragas.io/en/stable/concepts/metrics/available_metrics/faithfulness/?) utm_source=chatgpt.com], [trulens.org](https://www.trulens.org/blog/archive/2025/?utm_source=chatgpt.com))
4. reranking (the key to quality)
- Voyage rerank-2.5 (long 32k support, good latest bench) if API available. If fully local, bge-reranker-v2-m3 (multilingual). ([Voyage AI](https://blog.voyageai.com/2025/08/11/rerank-2-5/?utm_source=chatgpt.com), [Hugging Face [https://huggingface.co/BAAI/bge-](https://huggingface.co/BAAI/bge-) reranker-v2-m3?utm_source=chatgpt.com])
5. multi-stage inference orchestration
- LangGraph to graph "Plan→Collect→Verify→Summarize→Citation Formatting" (persistent memory possible). ([langchain-ai.github.io](https://langchain-ai.github.io/langgraph/?utm_source=chatgpt.com))
- Securely tool local FS with MCP (Model Context Protocol) and file references from agents. ([openai.github.io](https://openai.github.io/openai-agents-python/ja/mcp/?utm_source=chatgpt.com), [The Verge [https://www.theverge.com/](https://www.theverge.com/) news/669298/microsoft-windows-ai-foundry-mcp-support?utm_source=chatgpt.com])
6. citation and verification
- If you need a source, use PaperQA2 as the final generator / or use a Citekit system together. ([GitHub](https://github.com/Future-House/paper-qa?utm_source=chatgpt.com), [arXiv [https://arxiv.org/abs/2408.04662?utm_source=chatgpt](https://arxiv.org/abs/2408.04662?utm_source=chatgpt) .com])
7. long-text measures (context compression)
- Sentence/token-by-sentence pruning of LLMLingua-2 and Provence to remove stray context and reduce costs and illusions. ([Microsoft](https://www.microsoft.com/en-us/research/project/llmlingua/llmlingua-2/?utm_source=chatgpt.com), [proceedings.iclr.cc [https://proceedings.iclr.cc/paper_files/paper/2025/file/5e956fef0946dc1e39760f94b78045fe-Paper-Conference.pdf?utm_source=chatgpt.](https://proceedings.iclr.cc/paper_files/paper/2025/file/5e956fef0946dc1e39760f94b78045fe-Paper-Conference.pdf?utm_source=chatgpt.) com])
8. local execution infrastructure
- LLM execution is Ollama or LM Studio (GUI/API); MLX for Apple Silicon; VRAM is recommended to be model size +/-. ([ollama.com](https://ollama.com/?utm_source=chatgpt.com), [LM Studio](https://lmstudio.ai/?utm_source=chatgpt.com), [[GitHub https:// github.com/ml-explore/mlx-lm?utm_source=chatgpt.com]], [Windows Central [https://www.windowscentral.com/artificial-intelligence/when-it](https://www.windowscentral.com/artificial-intelligence/when-it) -comes-to-running-ollama-on-your-pc-for-local-ai-one-thing-matters-more-than-most-heres-why?utm_source=chatgpt.com])

Minimum configuration (CLI oriented) that works quickly
- Purpose: In-depth question to local PDF group -> answer with page citation
- Composition: Docling → LanceDB or Qdrant → Jina v3 embedded → bge-reranker-v2-m3 → PaperQA2
- Reasons: parsing accuracy, multilingual, fully on-premises, citation strength. ([GitHub](https://github.com/docling-project/docling?utm_source=chatgpt.com), [https://lancedb.com/?utm_source= chatgpt.com](https://lancedb.com/), [jina.ai](https://jina.ai/news/jina-embeddings-v3-a-frontier-multilingual-embedding-model/?utm_source=chatgpt.com), [Hugging Face](https://huggingface.co/BAAI/bge-reranker-v2-m3?utm_source=chatgpt.com))

Evaluation and Operation
- RAGAS/TruLens/ARES for periodic measurement of faithfulness / context relevance / answer relevance and AB for embedding, splitting and reranking ([docs.ragas.io [https://docs.ragas.io/en/](https://docs.ragas.io/en/) stable/concepts/metrics/available_metrics/faithfulness/?utm_source=chatgpt.com], [trulens.org [https://www.trulens.org/blog/archive/](https://www.trulens.org/blog/archive/) 2025/?utm_source=chatgpt.com], [arXiv](https://arxiv.org/abs/2311.09476?utm_source=chatgpt.com))
- Audit log: always save which pages of which files are cited (following Deep Research's "always source" philosophy). ([OpenAI Help Center](https://help.openai.com/en/articles/10500283-deep-research-faq?utm_source=chatgpt.com))

When in doubt, choose between these two options
1. strict citation and research type: PaperQA2 (generated) + Docling (parsed) + Jina v3 (embedded) + bge-reranker-v2-m3 (local). ([GitHub](https://github.com/Future-House/paper-qa?utm_source=chatgpt.com), [IBM Research [https://research.ibm.com/blog/docling-](https://research.ibm.com/blog/docling-) generative-AI?utm_source=chatgpt.com], [jina.ai [https://jina.ai/news/jina-embeddings-v3-a-frontier-multilingual-embedding-model/?utm](https://jina.ai/news/jina-embeddings-v3-a-frontier-multilingual-embedding-model/?utm) _source=chatgpt.com], [Hugging Face](https://huggingface.co/BAAI/bge-reranker-v2-m3?utm_source=chatgpt.com))
2. search, discovery and mapping: [[GraphRAG]] + LlamaIndex/LangGraph + [[Voyage rerank]] (or bge). ([Microsoft](https://www.microsoft.com/en-us/research/project/graphrag/?utm_source=chatgpt.com), [[microsoft.github.io https:// microsoft.github.io/graphrag/?utm_source=chatgpt.com]], [langchain-ai.github.io [https://langchain-ai.github.io/langgraph/?utm_source=](https://langchain-ai.github.io/langgraph/?utm_source=) chatgpt.com], [Voyage AI](https://blog.voyageai.com/2025/08/11/rerank-2-5/?utm_source=chatgpt.com))


---
This page is auto-translated from [/nishio/ローカルDeep Research](https://scrapbox.io/nishio/ローカルDeep Research) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
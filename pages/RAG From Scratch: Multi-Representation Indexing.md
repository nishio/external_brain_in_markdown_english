---
title: "RAG From Scratch: Multi-Representation Indexing"
---

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>
- The [[RAG From Scratch]] video series explains key RAG concepts in short, focused videos with code.
- The twelfth video focuses on tricks to help index the entire document.
- Many RAG approaches focus on splitting the document into chunks and getting several chunks for the LLM based on similarity to the input question, but setting the chunk size and number of chunks is difficult and if the LLM does not provide the full context for answering the question, impact the results.
- [[Proposition indexing]] (@tomchen0 et al) is a technique that uses LLM to generate search-optimized document summaries ("propositions") and is a useful idea.
- Based on this paper, we built two retriever:.
    - (1) multi-vector retriever embeds the summary, but returns the complete document to the LLM.
    - (2) parent-doc retriever embeds chunks, but also returns the complete document to the LLM.
- By using a concise representation (summary or chunk) suitable for retrieval, but linking to a document with full context for generation, one can get the best of both worlds.
- This approach is general and can be applied to tables and images: create and index summaries and return raw tables and images for LLM generation.
- This avoids the challenges of directly embedding tables (which can be split if the chunk size is improperly set) or images (which require multimodal embedding), and allows summaries to be used as representations for text-based similarity searches.

> [LangChainAI](https://twitter.com/LangChainAI/status/1773387841550323929/photo/1) RAG From Scratch: Multi-Representation Indexing
>
>  Our RAG From Scratch video series walks through impt RAG concepts in short / focused videos w/ code.
>
>  This is the 12th video in our series and focuses on some useful tricks for indexing full documents.
>
>   Problem: Many RAG approaches focus on splitting documents into chunks and retrieving some number based on similarity to an input question for the LLM. But chunk size and chunk number can be difficult to set and affect results if they do not provide full context for the LLM to answer a question.
>
>  Idea: Proposition indexing (
>  @tomchen0
>   et al) is a nice paper that uses an LLM to produce document summaries ("propositions") that are optimized for retrieval. We've built on this with two retrievers.
>
>  (1) multi-vector retriever embeds summaries, but returns full documents to the LLM. (2) parent-doc retriever embeds chunks but also returns full documents to the LLM. The idea is to get best of both worlds: use concise representations (summaries or chunks) that are well-suited to retrieval, but link them to documents, which have full context for generation.
>
>  The approach is general, and can also be applied to tables or images: create / index a summary, but return the raw table or raw image for LLM generation. This gets around challenges w/ directly embedding tables (they can be split by poorly tuned chunk size) or images (need multi-modal embeddings), using a summary as a representation for text-based similarity search.
>
>   Video:
>  [https://youtu.be/gTCU9I6QqCE](https://youtu.be/gTCU9I6QqCE)
>
>   Code:
>  [https://github.com/langchain-ai/rag-from-scratch/blob/main/rag_from_scratch_12_to_14.ipynb…](https://github.com/langchain-ai/rag-from-scratch/blob/main/rag_from_scratch_12_to_14.ipynb…)
>
>   References:
>  1/ Proposition indexing:  [https://arxiv.org/pdf/2312.06648.pdf…](https://arxiv.org/pdf/2312.06648.pdf…)
>  2/ Multi-vector:
>  [https://python.langchain.com/docs/modules/data_connection/retrievers/multi_vector…](https://python.langchain.com/docs/modules/data_connection/retrievers/multi_vector…)
>  3/ Parent-document:
>  [https://python.langchain.com/docs/modules/data_connection/retrievers/parent_document_retriever…](https://python.langchain.com/docs/modules/data_connection/retrievers/parent_document_retriever…)
>  4/ Blog applying this to tables:
>  [https://blog.langchain.dev/semi-structured-multi-modal-rag/…](https://blog.langchain.dev/semi-structured-multi-modal-rag/…)
>  5/ Blog applying this to images w/ eval:
>  [https://blog.langchain.dev/multi-modal-rag-template/…](https://blog.langchain.dev/multi-modal-rag-template/…)
>  ![image](https://pbs.twimg.com/media/GJxR6lWbIAA1ITr?format=jpg&name=900x900#.png)

---
This page is auto-translated from [/nishio/RAG From Scratch: Multi-Representation Indexing](https://scrapbox.io/nishio/RAG From Scratch: Multi-Representation Indexing) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
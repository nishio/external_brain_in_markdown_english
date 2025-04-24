---
title: "Towards Long Context RAG"
---

[Towards Long Context RAG — LlamaIndex, Data Framework for LLM Applications](https://www.llamaindex.ai/blog/towards-long-context-rag)
<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>
LlamaIndex offers his thoughts on how RAG architectures will evolve with the advent of large-context LLMs such as Google's Gemini 1.5 Pro.
While large-context LLMs solve problems such as tuning chunking algorithms and coordinating searches and chains of thought for single documents, challenges remain, such as searches for large document corpora, context length of embedded models, and cost and latency.
To address these challenges while leveraging the capabilities of large-context LLMs, a new RAG architecture is needed, and LlamaIndex proposes the following three
- Search from small chunks to large chunks
- Intelligent routing for latency and cost tradeoffs
- KV cache with search completion

# Large Context LLM Issues
.
1. limitations of search for large document corpora
        - - 1M tokens equals approximately 7 Uber SEC 10K filings
        - - 10M tokens equals about 70 filings, limited to about 40MB of data
        - - Many companies' knowledge corpora are in gigabytes or terabytes, and to build a system that leverages LLM for these knowledge corpora, we still need to build a way to get the data

2. context length delay of the embedded model
        - - Currently, the largest context window is 32k tokens in together.ai
        - - Chunks used for synthesis in large context LLMs can be made larger, but text chunks used for search still need to be much smaller

3. cost and waiting time issues
        - - It takes about 60 seconds to pack information into a 1M context window and could cost $0.50 to $20 at current prices
        - - Using the KV cache to cache document activations and reusing the same cache for subsequent generation may alleviate this problem

4. issues with KV cache
        - - Caching 1M tokens worth of activations requires about 100GB of GPU memory, or two H100s
        - - When the underlying corpus is large, there are also challenges in how to optimally manage the cache
        - - Since each activation is a function of all previous tokens, replacing a document in the KV cache will affect all subsequent activations of that document

These are the main challenges of large-context LLM. In order to address these challenges while taking full advantage of the capabilities of large-context LLMs, the development of a new RAG architecture is considered essential.

# New RAG architecture proposed by LlamaIndex
.

1. search from small chunks to large chunks
        - - When large-context LLMs require completion by search for large knowledge bases (in the order of gigabytes), they need to be indexed and searched from small chunks, with each chunk linked to a larger chunk that is ultimately input into the LLM during synthesis
        - - This can be accomplished in two ways: by indexing a summary of the document and linking it to the entire document, or by indexing a small chunk of the document and linking it to the document
        - - The reason for embedding and indexing small chunks is that the current embedding model's context length has not kept up with LLM, and that multiple fine-grained embedded representations may be more advantageous for retrieving relevant information than embedding entire documents

2. intelligent routing for latency/cost tradeoffs
        - - The amount of context appropriate for each use case should be carefully considered, taking into account the trade-off between cost and latency
        - - Existing RAG methods (top-k search and synthesis) are appropriate for questions asking for specific details
        - - More context is needed for summaries and complex questions that span multiple documents
        - - Assumes an intelligent routing layer on top of multiple RAG and LLM synthesis pipelines that can choose the best strategy in terms of cost and latency depending on the question

3. KV cache with search supplementation
        - - Using the KV cache to cache all document tokens in a context window eliminates the need to recalculate the activation of these tokens in subsequent conversations, significantly reducing latency and cost
        - - For knowledge corpora that exceed context length, it is assumed that a "caching by search" paradigm will emerge, in which users retrieve the most relevant documents they wish to use in their answers
        - - This includes alternating search strategies with traditional caching algorithms such as LRU caching
        - - Because location is important and the cached vector is a function of all tokens up to that location, not just the tokens in the document itself, replacing a chunk from the KV cache will affect all subsequent locationally generated cached tokens, which makes traditional KV cache architecture differs from the conventional KV cache architecture

These are the details of the new RAG architectures proposed by LlamaIndex. Through these architectures, we expect to address the challenges of large-context LLMs while maximizing their capabilities.
---
This page is auto-translated from [/nishio/Towards Long Context RAG](https://scrapbox.io/nishio/Towards Long Context RAG) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Hypothetical Document Embeddings"
---

[[Precise Zero-Shot Dense Retrieval without Relevance Labels]]
> While dense retrieval has been shown effective and efficient across tasks and languages, it remains difficult to create effective fully zero-shot dense retrieval systems when no relevance label is available. In this paper, we recognize the difficulty of zero-shot learning and encoding relevance. Instead, we propose to pivot through Hypothetical Document Embeddings~(HyDE). Given a query, HyDE first zero-shot instructs an instruction-following language model (e.g. InstructGPT) to generate a hypothetical document. The document captures relevance patterns but is unreal and may contain false details. Then, an unsupervised contrastively learned encoder~(e.g. Contriever) encodes the document into an embedding vector. This vector identifies a neighborhood in the corpus embedding space, where similar real documents are retrieved based on vector similarity. This second step ground the generated document to the actual corpus, with the encoder's dense bottleneck filtering out the incorrect details. Our experiments show that HyDE significantly outperforms the state-of-the-art unsupervised dense retriever Contriever and shows strong performance comparable to fine-tuned retrievers, across various tasks (e.g. web search, QA, fact verification) and languages~(e.g. sw, ko, ja).
- [https://arxiv.org/abs/2212.10496](https://arxiv.org/abs/2212.10496)

(DeepL) While dense search has been shown to be effective and efficient across tasks and languages, it remains difficult to create an effective full zero-shot dense search system when relevance labels are not available. In this paper, we recognize the difficulty of learning zero-shot and encoding relevance. Instead, we propose pivoting via [[Hypothetical Document Embeddings]] ([[HyDE]]). Given a query, HyDE first instructs a zero-shot instruction-following language model (e.g., [[InstructGPT]]) to generate a virtual document. This document captures relevance patterns, but is unrealistic and may contain incorrect details. Next, an unsupervised contrast-trained encoder~ (such as [[Contriever]]) encodes the document into an [[embedded vector]]. This vector identifies neighborhoods in the embedding space of the corpus and searches for similar actual documents based on vector similarity. This second step grounds the generated documents to the actual corpus by filtering out details where the encoder's dense bottleneck is imprecise. Our experiments show that HyDE significantly outperforms Contriever, a state-of-the-art unsupervised dense-text search, and performs strongly on a variety of tasks (e.g., web search, QA, fact checking) and languages (e.g., sw, ko, ja), comparable to fine-tuned search.

> This second step grounds the generated documents to the actual corpus by filtering out details where the encoder's dense bottleneck is inaccurate.
- Here's the interesting part: even if you're unlucky enough to get a halucination in step 1, they claim that it won't interfere with the search because the low probability details will be dropped at the stage of embedding it in the vector.


> Instead of encoding the user's query and retrieving the relevant documents, it generates and encodes a "hypothetical" answer. Documents with correct answers are more like wrong answers than questions.
- > [@goodside](https://twitter.com/goodside/status/1615383151987294209): Clever paper — [[HyDE]]: Hypothetical Document Embeddings
- > Instead of encoding the user's query to retrieve relevant documents, generate a "hypothetical" answer and encode that. Documents with right answers more similar to wrong answers than to questions. [https://t.co/Yayyu92Olu](https://t.co/Yayyu92Olu)
- > ![image](https://pbs.twimg.com/media/Fmr8uVYaEAEg_Ik.jpg)

A technique that [[blu3mo]] taught me before, with a name like this.

---
This page is auto-translated from [/nishio/Hypothetical Document Embeddings](https://scrapbox.io/nishio/Hypothetical Document Embeddings) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
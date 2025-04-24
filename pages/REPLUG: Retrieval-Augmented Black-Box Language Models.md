---
title: "REPLUG: Retrieval-Augmented Black-Box Language Models"
---

> We introduce [[REPLUG]], a retrieval-augmented language modeling framework that treats the language model (LM) as a black box and augments it with a tuneable retrieval model. Unlike prior retrieval-augmented LMs that train language models with special cross attention mechanisms to encode the retrieved text, REPLUG simply prepends retrieved documents to the input for the frozen black-box LM. This simple design can be easily applied to any existing retrieval and language models. Furthermore, we show that the LM can be used to supervise the retrieval model, which can then find documents that help the LM make better predictions. Our experiments demonstrate that REPLUG with the tuned retriever significantly improves the performance of GPT-3 (175B) on language modeling by 6.3%, as well as the performance of Codex on five-shot MMLU by 5.1%.
[https://arxiv.org/abs/2301.12652](https://arxiv.org/abs/2301.12652)
(DeepL)We introduce REPLUG, a search augmented language model framework that treats language models (LMs) as black boxes and augments them with tunable search models. Unlike prior retrieval augmented LMs that train language models using special cross-attention mechanisms to encode retrieved text, REPLUG simply adds retrieved documents to the input of a frozen black box LM. This simple design can be easily adapted to existing search and language models. Furthermore, by using the LM to supervise the retrieval model, we show that the LM can find documents to make better predictions. Our experiments demonstrate that REPLUG with a tuned retriever improves the performance of GPT-3(175B) language modeling by 6.3% and Codex's 5-shot MMLU by 5.1%.

[REPLUG: Retrieve and Plug - arXiv Latest Papers](https://devneko.jp/wordpress/?p=2884)

[[RAG]]: [[Retrieval-Augmented Generation]]
- [[Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks]] put it in the internal state, but why should it be a RAG to be given to a prompt? I was wondering.

submitted 2023-01-30

---
This page is auto-translated from [/nishio/REPLUG: Retrieval-Augmented Black-Box Language Models](https://scrapbox.io/nishio/REPLUG: Retrieval-Augmented Black-Box Language Models) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
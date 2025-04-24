---
title: "Retrieval meets Long Context Large Language Models"
---

> Extending the context window of large language models (LLMs) is getting popular recently, while the solution of augmenting LLMs with retrieval has existed for years. The natural questions are: i) Retrieval-augmentation versus long context window, which one is better for downstream tasks? ii) Can both methods be combined to get the best of both worlds? In this work, we answer these questions by studying both solutions using two state-of-the-art pretrained LLMs, i.e., a proprietary 43B GPT and LLaMA2-70B. Perhaps surprisingly, we find that LLM with 4K context window using simple retrieval-augmentation at generation can achieve comparable performance to finetuned LLM with 16K context window via positional interpolation on long context tasks, while taking much less computation. More importantly, we demonstrate that retrieval can significantly improve the performance of LLMs regardless of their extended context window sizes. Our best model, retrieval-augmented LLaMA2-70B with 32K context window, outperforms GPT-3.5-turbo-16k and Davinci003 in terms of average score on seven long context tasks including question answering and query-based summarization. It also outperforms its non-retrieval LLaMA2-70B-32k baseline by a margin, while being much faster at generation. Our study provides general insights on the choice of retrieval-augmentation versus long context extension of LLM for practitioners.
[https://arxiv.org/abs/2310.03025](https://arxiv.org/abs/2310.03025)

> [sla](https://twitter.com/sla/status/1710575129787281478/photo/1) NVIDIA paper examining whether RAG (information completion through search) or input/output length expansion is more effective for LLM in a Q&A and summary task.
>  ・ [[RAG]] improves performance regardless of input length
>  ・4k + RAG can infer faster with almost the same accuracy as 16k
>  ・RAG有りLLaMA2-70B-32k outperforms GPT-3.5-turbo-16k and Davinci003 for best performance
>  ![image](https://pbs.twimg.com/media/F70uxoWXMAELZPN?format=jpg&name=medium#.png)
- > [_philschmid](https://twitter.com/_philschmid/status/1710575129787281478/photo/1) RAG or longer context windows - what performs better?  A new study from
- >  @nvidia
- >    compares retrieval augmentation generation (RAG) with increasing context window for large language models (LLMs) on long context question answering and summarization tasks.
- >  ![image](https://pbs.twimg.com/media/F70uxoWXMAELZPN?format=jpg&name=medium#.png)

- > [_philschmid](https://twitter.com/_philschmid/status/1710575131968356622) Started from two base LLMs; NVIDIA created 43B GPT and Llama 2 70B.
- >   Extended context window to 16k for GPT-43B and 16K/32k for Llama using positional interpolation using the PILE dataset
- >   Instruction-tuned small and big context models on QA and summarization

- > [_philschmid](https://twitter.com/_philschmid/status/1710575133444751822) Used 3 different Retriever (Dragon, Contriever, OpenAI embeddings) to embed and retrieve relevant context chunks.
- >   Evaluated on 7 datasets
- >   Compare the performance of LLM + Retrieval for 4k & 16k/32k against non-retrieval with full context. Also, compare to GPT-3.5-turbo

- > [_philschmid](https://twitter.com/_philschmid/status/1710575134954631557) Open source Embedding Models/Retriever outperform OpenAI models
- >   The chunk size for embedding was 300 words
- >   The best performance of RAG was for 5-10 chunks
- >   Simple RAG + 4k LLM can match long context LLM.
- >   RAG + 32k LLM performs better than providing the full context

- > [_philschmid](https://twitter.com/_philschmid/status/1710575136657600958) RAG Llama 2 70B outperforms GPT-3.5-turbo-16k (non-RAG).
- >   Positional interpolation is a simple method to extend context length by ~4-8x
- >
- >  Check out the full paper [https://arxiv.org/abs/2310.03025](https://arxiv.org/abs/2310.03025)

---
This page is auto-translated from [/nishio/Retrieval meets Long Context Large Language Models](https://scrapbox.io/nishio/Retrieval meets Long Context Large Language Models) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
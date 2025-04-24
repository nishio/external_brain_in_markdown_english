---
title: "Variational Open-Domain Question Answering"
---

[https://arxiv.org/abs/2210.06345](https://arxiv.org/abs/2210.06345)
<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>
- Research Abstract: Few studies have used [[variational reasoning]] in the optimization of retrieval augmentation models ([[RAG]]), which have shown effectiveness in natural language processing tasks. This study introduces a variational open domain (VOD) framework that enables end-to-end training and evaluation of retrieval extension models.
- VOD framework: approximates the marginal likelihood of a task using [[Réyni variational bounds]] based on self-normalized estimates. Provides a tractable approach that can also handle retriever distributions in large corpora.
- Implementation results: the BioLinkBERT model was trained on MedMCQA, a multiple-choice format dataset on medical exam questions, and outperforms the MedPaLM model. High accuracy was achieved despite a much smaller number of parameters.
- Application to medical semantic search: demonstrating the effect of the learned retriever component in semantic search in a medical context.

---
This page is auto-translated from [/nishio/Variational Open-Domain Question Answering](https://scrapbox.io/nishio/Variational Open-Domain Question Answering) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
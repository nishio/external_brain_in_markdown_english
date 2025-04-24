---
title: "Universal Information Extraction"
---

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>
Universal Information Extraction ([[UIE]]) is a methodology for solving multiple information extraction tasks in a unified manner using a single language model UIE was proposed in an ACL paper in 2022.

The main features of the UIE are as follows
- Various information extraction tasks (e.g., eigenexpression extraction, relation extraction, event extraction, etc.) are expressed in a unified manner using a combination of two operations: spot and asoc.
- SPOT represents an operation to extract target parts (entities, etc.) from a sentence, and ASOC represents an operation to extract relations between SPOTs.
- The extraction results are output in a structured format (Structured Extraction Lang Edge, SEL).
- Solve all tasks with only one language model (pre-trained models such as T5 and BART in the paper).

Advantages of UIE include the ease of model management because a single model can solve a variety of tasks, the ability to share knowledge among tasks, and the ability to learn with little data.

UIE is further developed by combining it with pre-trained language models and is a pioneering study in the use of language models in information extraction tasks. The method is attracting attention as a unified framework for information extraction.

I guess this is it.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
[Unified Structure Generation for Universal Information Extraction - ACL Anthology](https://aclanthology.org/2022.acl-long.395/)

---
This page is auto-translated from [/nishio/Universal Information Extraction](https://scrapbox.io/nishio/Universal Information Extraction) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
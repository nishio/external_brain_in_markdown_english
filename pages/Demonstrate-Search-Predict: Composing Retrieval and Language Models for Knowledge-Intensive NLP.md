---
title: "Demonstrate-Search-Predict: Composing Retrieval and Language Models for Knowledge-Intensive NLP"
---


[2212.14024 Demonstrate-Search-Predict: Composing retrieval and language models for knowledge-intensive NLP](https://arxiv.org/abs/2212.14024)
<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>This paper proposes a new framework, DEMONSTRATE-SEARCH-PREDICT (DSP), which combines a language model (LM) and a retrieval model (RM). The main points are as follows.
1. DSP can build a pipeline to solve complex knowledge-intensive tasks by exchanging natural language text between LM and RM.
2. the DSP program consists of three stages: automatic generation of demonstrations (DEMONSTRATE), retrieval of relevant information (SEARCH), and grounded forecasting (PREDICT).
3. DEMONSTRATE automatically annotates intermediate pipeline representations from a small number of training examples; SEARCH rewrites questions and performs multi-hop searches that take into account the context of the dialogue; PREDICT merges multiple search results to produce a final output; and DEMONSTRATE automatically annotates the pipeline with a small number of training examples.
4. applied the DSP program to three tasks: open-domain question-and-answer, multi-hop question-and-answer, and dialogue question-and-answer, and achieved 37-120% accuracy improvement over existing methods.
5. showed the potential of DSP to combine pre-trained LM and RM as modules to develop AI systems that can quickly adapt to new domains.
The DSP is a framework that provides the foundation for a more sophisticated in-context learning system by successfully linking LM and RM.
---
This page is auto-translated from [/nishio/Demonstrate-Search-Predict: Composing Retrieval and Language Models for Knowledge-Intensive NLP](https://scrapbox.io/nishio/Demonstrate-Search-Predict: Composing Retrieval and Language Models for Knowledge-Intensive NLP) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
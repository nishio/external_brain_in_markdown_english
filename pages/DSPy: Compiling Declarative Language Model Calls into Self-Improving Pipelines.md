---
title: "DSPy: Compiling Declarative Language Model Calls into Self-Improving Pipelines"
---

[2310.03714 DSPy: Compiling Declarative Language Model Calls into Self-Improving Pipelines](https://arxiv.org/abs/2310.03714)
<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>This paper proposes a programming model DSPy for pipeline construction using a language model (LM). The main points are as follows
- DSPy abstracts LM calls into [[declarative modules]] and combines them to build [[text transformation graphs]].
- The DSPy module is parameterized and can learn and combine techniques such as prompting, fine tuning, data augmentation, and inference.
- The DSPy compiler optimizes any DSPy program to maximize the specified metrics.
- In case studies of math sentence problems and multi-step question answering, a few lines of DSPy programs self-improved GPT-3.5 and Llama2-13b, outperforming hand-made prompts in a short time.
- Even an open and relatively small LM, such as the T5 with 770M parameters, could build a high-performance pipeline with DSPy.
DSPy provides a foundation for streamlining and upgrading the construction of LM-based systems by modularizing the LM pipeline and automating the optimization of prompts.

---
This page is auto-translated from [/nishio/DSPy: Compiling Declarative Language Model Calls into Self-Improving Pipelines](https://scrapbox.io/nishio/DSPy: Compiling Declarative Language Model Calls into Self-Improving Pipelines) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
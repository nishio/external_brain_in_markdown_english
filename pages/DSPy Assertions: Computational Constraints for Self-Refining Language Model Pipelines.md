---
title: "DSPy Assertions: Computational Constraints for Self-Refining Language Model Pipelines"
---

[2312.13382 DSPy Assertions: Computational Constraints for Self-Refining Language Model Pipelines](https://arxiv.org/abs/2312.13382)
<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>This paper proposes LM Assertions, a new programming construct for expressing computational constraints on language model (LM) pipelines. The main points are as follows.
1. LM Assertions are Boolean expressions that represent the conditions that the output of LM must satisfy; there are two types, Assert and Suggest; Assert stops the pipeline for a major constraint violation, while Suggest suggests a minor constraint violation.
2. integrate LM Assertions into the DSPy programming model and define backtracking/retry semantics for constraint violations. When a constraint is violated, the LM is given the previous output and error message to regenerate.
3. LM Assertions can be used to automatically generate examples that satisfy constraints and can be used to optimize the LM pipeline. Also, counterexamples of constraint violations and their corrections can be generated automatically.
4. evaluated on four tasks, LM Assertions significantly increased the percentage of pipelines satisfying constraints (up to 164%) and the percentage of high-quality outputs (up to 37%).
5. although there are some issues such as conflicts between constraints, LM Assertions allows developers to specify desired computational constraints in the LM pipeline and have them satisfied automatically.
LM Assertions can be said to provide the foundation for building a more advanced reliable LM pipeline.

---
This page is auto-translated from [/nishio/DSPy Assertions: Computational Constraints for Self-Refining Language Model Pipelines](https://scrapbox.io/nishio/DSPy Assertions: Computational Constraints for Self-Refining Language Model Pipelines) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
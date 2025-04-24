---
title: "Chain of Thought"
---

# Written by a human being in 2023
Chain-of-Thought Prompting Elicits Reasoning in Large Language Models
- We explore how generating a chain of thought—a series of intermediate reasoning steps—significantly improves the ability of large language models to perform complex reasoning. In particular, we show how such reasoning abilities emerge naturally in sufficiently large language models via a simple method called chain-ofthought prompting, where a few chain of thought demonstrations are provided as exemplars in prompting.
- Experiments on three large language models show that chain-of-thought prompting improves performance on a range of arithmetic, commonsense, and symbolic reasoning tasks. The empirical gains can be striking. For instance, prompting a PaLM 540B with just eight chain-of-thought exemplars achieves state-of-the-art accuracy on the GSM8K benchmark of math word problems, surpassing even finetuned GPT-3 with a verifier.
- [https://arxiv.org/pdf/2201.11903.pdf](https://arxiv.org/pdf/2201.11903.pdf)
(DeepL)Thought Chain Prompting for Eliciting Inference in Large Language Models
- We explore how the generation of chains of thoughts (a series of intermediate inference steps) can significantly improve the ability of large language models to perform complex inferences. In particular, we show that such reasoning abilities emerge naturally in sufficiently large language models by a simple method called thought chain prompting, in which several thought chain demonstrations are provided as exemplars for the prompts.
- Experiments with three large-scale language models show that thought chain prompts improve performance on arithmetic, common sense, and symbolic reasoning tasks. The empirical improvements are significant. For example, by providing the PaLM 540B with only 8 thought-chain prompts, it achieved state-of-the-art accuracy on the GSM8K benchmark for math word problems, outperforming even the GPT-3, which was fine-tuned using a validator.

![image](https://gyazo.com/f21f8aafa600f51e984c7de12c2a3d7e/thumb/1000)
[[LangChain Glossary]]

I'm not good at inference tasks, so I'm going to improve with Prompting.
- Include the thought process in the case study.

Chain-of-Thought Prompting Elicits Reasoning in Large Language Models
[https://arxiv.org/abs/2201.11903](https://arxiv.org/abs/2201.11903)

[[Zero-Shot CoT]]

# Written in 2025 (+ commentary by AI)
[[Chain-of-Thought Prompting Elicits Reasoning in Large Language Models]]
[https://arxiv.org/abs/2201.11903](https://arxiv.org/abs/2201.11903)
I was surprised that some people didn't know about 2025-02-01 [[CoT]], but if you think about it calmly, it's a 2022 paper, so it's normal not to know about it
- After three years, the technology has reached a level where it is "natural to use" and models are trained to use it.
- [[GPT o1]] and [[DeepSeek]] make this thought process visible to the end user.

## [[o3-mini-high]]
This document summarizes a detailed study of the Chain-of-Thought (CoT) Prompting method and its effectiveness in large-scale language models.

[Main Points
- What is Chain-of-Thought Prompting?
    - It is a method that enables complex multi-step reasoning by generating not only a final answer to a problem, but also intermediate reasoning processes (chains of thoughts).

- experimental results
    - In mathematical problems (GSM8K, SVAMP, ASDiv, AQuA, MAWPS) and common sense and symbolic reasoning tasks (CSQA, StrategyQA, Date Understanding, Sports Understanding, SayCan), CoT Prompting In the case of CoT Prompting, a significant performance improvement over conventional few-shot prompting was confirmed.
    - The effect of the CoT was particularly noticeable as the model size increased (e.g., PaLM 540B, GPT-3 175B).

- Robustness and error analysis
    - Multiple prompt examples and descriptions by different annotators confirmed the effectiveness of the method, and methods to compensate for calculation errors and incorrect handling of symbols by an external calculator were also considered.

[Conclusion.
Chain-of-Thought Prompting has shown significant performance improvement in tasks that require complex multi-step inference compared to conventional single-response prompting, and is considered a very promising approach for future large-scale language model utilization and task application.

## o1 Pro
<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
Summary (concise version)
Chain-of-Thought Prompting" is a method that greatly improves the performance of complex inference problems (arithmetic problems, common sense reasoning, symbolic manipulation, etc.) by providing a large language model with a small sample of intermediate inference processes (chain-of-thought) for the solution. This is a method that greatly improves the performance of complex inference problems (arithmetic problems, common sense reasoning, symbolic manipulation, etc.) by providing a small number of examples. Especially for models with tens to hundreds of billions of parameters, it provides significant accuracy gains over conventional "just-answer" prompts, and has, for example, outperformed the state-of-the-art for a set of math problems (GSM8K). Interestingly, the effectiveness of chain-of-sorting becomes apparent from "above a certain size" (the effect is small for small-scale models). Chain-of-sorting also allows visualization of intermediate inferences, but not all inferences are correct, which is an issue for future work.

Explanation (Explanation of key points)
- Background and inspiration
    - Conventional large-scale language models are often weak in complex inference with prompts that directly map "input→output.
    - If we present several examples of "writing down the thought process (steps of inference) in natural language" and have the model itself output the steps before answering the question, the accuracy of inference is greatly improved.

- Method: Chain-of-Thought Prompting
    - Several examples are presented in the form of "problem -> (thought process statement) -> final answer".
    - The model comes to its conclusion without training or additional parameter updates, while generating intermediate inference sentences based on the presented examples.

- Characteristics of experimental results
    - Noticeable performance improvement in arithmetic text problems (e.g., GSM8K): as an example, the PaLM 540B model achieves SOTA that exceeds existing methods through chain-of-sorts.
    - Common sense reasoning and symbolic manipulation were also effective, with Chain-of-Thought Prompting greatly increasing response accuracy.
    - The small models showed little improvement, confirming the "emergent capability "** that "the effect is more pronounced in the large models "**.

- Additional Analysis
    - Transformations such as simply having the middle write "just the formula" will have little effect, and "following the steps in natural language" is key.
    - There is some influence on how the chain-of-sort is written and how the sample examples are chosen, but by and large all annotation styles exceed the standard prompts.
    - Even if the answer is correct, part of the inference process may be incorrect, or conversely, the result may be wrong even if it is correct up to the halfway point (the content of the inference cannot be absolutely trusted).

- Significance and Challenges
    - Significance: Noted as a simplified method that brings out the potential of large-scale models to handle complex thought steps, as compared to traditional "answer only" output.
    - Challenges: Logical consistency is not always guaranteed, and practical hurdles remain, such as computational cost and size dependence.

The main point of this research is that it showed that simply "clearly indicating the thought process along with appropriate examples" can greatly increase the multi-stage inference capability of large-scale language models. In other words, the key point is the finding that if a model takes advantage of a large number of parameters, multi-stage inference is possible simply by presenting a small number of examples in the form of a chain of sorts.


---
This page is auto-translated from [/nishio/Chain of Thought](https://scrapbox.io/nishio/Chain of Thought) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
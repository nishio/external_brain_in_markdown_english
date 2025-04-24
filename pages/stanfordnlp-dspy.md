---
title: "stanfordnlp/dspy"
---

- [[Automated Prompt Engineering]]
[https://github.com/stanfordnlp/dspy](https://github.com/stanfordnlp/dspy)
<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>[[DSPy]] is a framework for optimizing language model (LM) prompts and weights, especially when LMs are used more than once in the pipeline.DSPy separates the program flow (modules) and the parameters of each step (LM prompts and weights), and then uses the LM driven algorithm to adjust the prompts and weights to maximize the specified metric.

Using DSPy, powerful models such as GPT-3.5 and GPT-4 can be tailored to be more reliable for a task; DSPy's optimizer compiles the same program into instructions, few-shot prompts, and weight updates appropriate for each LM. This allows the LMs and their prompts to be treated as optimizable parts of the system that can be learned from the data.

In short, DSPy allows us to tackle difficult tasks with a systematic approach instead of hacking prompts and manually generating data.

There are several major papers related to DSPy.
- "[[DSPy: Compiling Declarative Language Model Calls into Self-Improving Pipelines]]" (October 2023).
    - This paper provides an overview of the DSPy framework and the main ideas behind it. It introduces the concept of compiling declarative language model invocations into a self-improving pipeline and details the design and implementation of DSPy.
- "[[DSPy Assertions: Computational Constraints for Self-Refining Language Model Pipelines]]" (December 2023).
    - This paper introduces the concept of DSPy assertions. It guides the self-improvement process by imposing constraints on the behavior of the language model pipeline. We formulate assertions and show how they can help improve the quality of DSPy programs.
- "[[Demonstrate-Search-Predict: Composing Retrieval and Language Models for Knowledge-Intensive NLP]]" (December 2022).
    - This paper introduces the Demonstrate-Search-Predict (DSP) framework, the predecessor to DSPy. DSPy is a further development of this idea.

These papers demonstrate the evolution of DSPy and provide the key ideas and technical details of the framework; it would be beneficial to refer to these papers for a deeper understanding of DSPy.


> [hrjn](https://twitter.com/hrjn/status/1786994101646414236) I've been wondering about dspy since Nishio's post. i haven't touched it yet, so I'm not sure, but I guess that means it does prompt optimization best practices on its own. I wonder if it is a framework.
>  If langchain is IFTTT, DSpy is pytorch?scrapbox.io

> [nishio](https://twitter.com/nishio/status/1787021308116787515) I wrote a more detailed one. If the objective function can be defined in a lightweight way (and the percentage of correct answers in QA is so), then the prompt can be automatically tuned by iterating on changing the prompt and calculating the score, which is the rough direction of technological evolution, I think.
> [[DSPy]]

> [nishio](https://twitter.com/nishio/status/1787021799521472553) If we consider the prompt as a space of hyperparameters, it is discrete and ultra-high dimensional, so it seems difficult to tune it efficiently, and what if we can't implement the objective function in a lightweight way? What do you do when you can't implement the objective function in a lightweight way? What do you do when you can't implement the objective function in a lightweight way?


---
This page is auto-translated from [/nishio/stanfordnlp/dspy](https://scrapbox.io/nishio/stanfordnlp/dspy) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
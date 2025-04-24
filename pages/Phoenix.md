---
title: "Phoenix"
---

This article describes how to evaluate a large-scale language model (LLM). The main points are as follows
- As more applications use LLMs, measuring LLM performance becomes more important, but this is not easy
- A distinction should be made between evaluation of the LLM model itself (model evaluation) and evaluation of the system using LLM (system evaluation).
- System evaluation focuses on evaluation of areas that can be controlled by the developer, such as prompt templates, context, etc.
- Evaluation metrics vary by use case (information extraction, question and answer, RAG, etc.)
- It is effective to use the LLM itself for evaluation. Benchmark the accuracy of the LLM evaluation using correct data and apply it to the production system.
    1. first prepare a "golden data set" for the evaluation. This is representative of the type of data expected in the evaluation and includes manually labeled correct answers.
    - Next, select an LLM for evaluation. This may be different from the LLM used in the system under evaluation. Consider the balance between cost and accuracy.
    3. create an evaluation prompt template. Define the structure of the input (e.g., retrieved documents, user queries, etc.), what you want the LLM to do (e.g., determine document relevance), and the expected output format (e.g., related/unrelated binary).
    4. run the evaluation against the golden dataset and calculate metrics such as correctness, fit, and repeatability to benchmark. Improving the prompt template to increase accuracy will be an iterative process.
    5. performance on a golden data set with optimized prompt templates is a measure of the reliability of the evaluation. Although less accurate than manually, it is an inexpensive way to evaluate large amounts of data.
- Overall percentage of correct answers is not sufficient as an evaluation indicator, but should look at fit and repeatability
- Evaluations are conducted at pre-development, pre-production, and post-production timings
- Which model to use for evaluation depends on the use case, but the tradeoffs need to be understood
    - Balance between cost and accuracy. The larger and better performing the model, the better the quality of the evaluation, but also the more expensive.
    - Balance between reproducibility and conformance. Which is more important depends on the use case.
    - To what extent should the models for evaluation and production be matched? Although matching the characteristics of the models will increase the accuracy of the evaluation, a general-purpose model for evaluation can be used more easily.

Overall, the content was that evaluating LLM systems is an important but difficult task, and that best practices, tools, and data sets are being developed.

---
This page is auto-translated from [/nishio/Phoenix](https://scrapbox.io/nishio/Phoenix) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
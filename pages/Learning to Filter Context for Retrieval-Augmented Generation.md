---
title: "Learning to Filter Context for Retrieval-Augmented Generation"
---

> On-the-fly retrieval of relevant knowledge has proven an essential element of reliable systems for tasks such as open-domain question answering and fact verification. However, because retrieval systems are not perfect, generation models are required to generate outputs given partially or entirely irrelevant passages. This can cause over- or under-reliance on context, and result in problems in the generated output such as hallucinations. To alleviate these problems, we propose FILCO, a method that improves the quality of the context provided to the generator by (1) identifying useful context based on lexical and information-theoretic approaches, and (2) training context filtering models that can filter retrieved contexts at test time. We experiment on six knowledge-intensive tasks with FLAN-T5 and LLaMa2, and demonstrate that our method outperforms existing approaches on extractive question answering (QA), complex multi-hop and long-form QA, fact verification, and dialog generation tasks. FILCO effectively improves the quality of context, whether or not it supports the canonical output.
[https://arxiv.org/abs/2311.08377](https://arxiv.org/abs/2311.08377)
(DeepL)
- On-the-fly retrieval of relevant knowledge has proven to be an essential component of reliable systems for tasks such as open domain question answering and fact verification. However, because retrieval systems are not perfect, generative models must generate output from partially or completely irrelevant sentences. This can lead to over-reliance or under-reliance on context and can cause hallucination-like problems with the generated output. To alleviate these problems, we propose FILCO, a method that (1) identifies useful contexts based on lexical and information-theoretic approaches and (2) trains a context-filtering model that can filter retrieved contexts at test time, thereby improving the quality of the context provided to the generator by We experiment with FLAN-T5 and LLaMa2 on six knowledge-intensive tasks and demonstrate that our method outperforms existing approaches on extractive question answering (QA), complex multi-hop and long-text QA, fact verification, and dialogue generation tasks. FILCO is a regular effectively improves context quality with or without output support.

<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>This paper describes FILCO, a context filtering method for generative models in knowledge-intensive tasks. The main points are summarized below.

- PAPER CONTENT: The paper focuses on real-time retrieval of relevant knowledge, which is important for tasks such as open-domain question answering and fact verification. Current generation models may receive partial or completely irrelevant documents from incomplete search systems, which can cause problems in the generated output (e.g., generation of incorrect information) FILCO aims to filter context and improve the quality of the generation process 19†source].

- Comparison with previous studies: previous studies typically used retrieved information indiscriminately as generative input, which often contained irrelevant or misleading content; FILCO filters retrieved information on a fine-grained sentence-by-sentence basis to improve the quality of context [[20†source]] [[21†source]].

- Core technique/methodology: FILCO filters retrieved contexts based on (i) whether the sentence contains a generated output (STRINC), (ii) unigram overlap between content and output (LEXICAL), and (iii) the probability of a generated output given the content (conditional mutual information content (CXMI) based method [[21†source]].
    - > In this paper, we propose FILCO (§2), a method that learns to FILter COntext retrieved in a fine- grained sentence-wise manner, by training on con- tent selected via three measures: (i) STRINC: whether passages contain the generation output, (ii) LEXICAL overlap: how much unigram overlap the content and output has, and (iii) Conditional cross-mutual information (CXMI): how much more likely the generator is to generate the output when the content is provided.

- METHOD VALIDATION: The method was validated on six knowledge-intensive tasks, including extractive QA, complex multi-hop QA, long-text QA, fact verification, and dialogue generation, using the FLAN-T5 and LLAMA2 models. As a result, FILCO performed better than the basic approach on these tasks [[24†source]] [[25†source]] [[27†source]].

- Discussion/Criticism: researchers compared FILCO with other filtering strategies and discussed the most appropriate filtering methods for different tasks. For example, STRINC was shown to be most effective for extractive tasks, LEXICAL for dialogue generation, and CXMI for more complex tasks [[30†source]] [[31†source]].
    - ![image](https://gyazo.com/d20072972ba80021a2690ed27e18ad89/thumb/1000)

- RECOMMENDED FOLLOW-UP READINGS: Related studies have explored optimization on post-processing and generation of search results, retrieval of information at different granularities, etc. Previous studies related to FILCO include Lewis et al. (2020), Guu et al. (2020), Mi alon et al. (2023 ), Wang et al. (2019), Asai et al. (2022), and others [[32†source]].

The paper proposes a novel approach to improve the contextual quality of generative models in knowledge-intensive tasks and demonstrates its effectiveness. It also suggests appropriate context filtering strategies for different tasks.







---
This page is auto-translated from [/nishio/Learning to Filter Context for Retrieval-Augmented Generation](https://scrapbox.io/nishio/Learning to Filter Context for Retrieval-Augmented Generation) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Multi-turn intent classification"
---

Intent-Aware Dialogue Generation and Multi-Task Contrastive Learning for Multi-Turn Intent Classification
[https://arxiv.org/abs/2411.14252](https://arxiv.org/abs/2411.14252)

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>
The following paper proposes a framework for automatically generating large multilingual and domain-specific multiturn dialogue data and using it to improve the accuracy of multiturn [[intent classification]] (hereafter MTIC). The outline is as follows.

# Abstract of the paper (points)
.
1.### Purpose
.
    - Dialogue data in specific domains, such as online e-commerce, often have a large number of intents and span multiple languages. Since it is costly to manually collect sufficient multi-turn dialogue data, we propose a new framework for automatic generation of dialogue data.

2.### Proposed Method (Chain-of-Intent)
]
    - First, the "distribution of conversational turns" and "probability of intent transition" are learned using HMM (Hidden Markov Model), and the number of turns and intent sequence are sampled.
        - A large-scale language model (LLM) is then used to generate questions (user utterances) and answers (chatbot utterances) for each turn.
    - Combining "Chain-of-Intent sampling" (Chain-of-Intent) with HMM and natural sentence generation with LLM, we obtain a consistent multi-turn dialogue.

3.### Dataset (MINT-E)
.
    - This generation method was used to create MINT-E, multilingual multi-turn dialogue data for the EC domain.
        - Large corpus of 8 language markets (e.g., Indonesian, Vietnamese, English, etc.) and 381 different intents.

4.### Application to MTIC model (MINT-CL)
.
    - The "multi-turn intent classification (MTIC)" model is trained using the generated dialogue data.
        - In addition, "Multi-Task Learning + Contrastive Learning (Multi-Task Learning)" was introduced to further refine the expression by having the task of ranking good and bad answers learned in parallel.
    - This improves the accuracy of intent estimation.

5.### Experiments and Results
.
    - Quality evaluation of generated dialogues by GPT-4 and intent classification performance evaluation using actual chat logs.
        - When multi-turn dialogues generated by the proposed method are incorporated into the training data, intent classification accuracy improves. Significant improvement is seen mainly in English-speaking countries. There is improvement even for low-resource languages, but the study also points out the issue of quality differences depending on the language performance of the LLM.

# brief description
- [The main focus is to efficiently generate "dialogue data with many intentions ([[intent]]) and across multiple turns" and to create a highly accurate intent classification model.
- It features a two-step method, whereby the HMM explicitly models "intent transitions" and then the LLM creates natural and contextually consistent questions and answers.
- In addition to learning on the generated large-scale data (MINT-E), classification performance is further improved by combining "contrast learning to distinguish between good and bad answers" (MINT-CL).
- A future challenge is how to generate high-quality dialogue for languages for which the LLM language model has not been adequately trained (low-resource languages).

private chat [https://chatgpt.com/c/679b38fa-ba68-8011-8415-69cf8843434a](https://chatgpt.com/c/679b38fa-ba68-8011-8415-69cf8843434a)

---
This page is auto-translated from [/nishio/マルチターンのインテント分類](https://scrapbox.io/nishio/マルチターンのインテント分類) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
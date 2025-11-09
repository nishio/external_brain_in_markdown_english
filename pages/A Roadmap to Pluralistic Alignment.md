---
title: "A Roadmap to Pluralistic Alignment"
---

[A Roadmap to Pluralistic Alignment](https://arxiv.org/abs/2402.05070v1?utm_source=chatgpt.com)
<img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>Purpose of the Paper
- Using LLM as an example, we will summarize the conceptual framework and research issues for realizing and evaluating "pluralistic alignment," and point out the limitations of conventional RLHF and other methods.

Why Plurality?
- User diversity: Optimization for average preferences [[minority values are treated as noise]].
- Customizability: For fine adjustments within the safety guardrail, it must be explicit which value axes can be operated.
- Technical advantage: Multidimensional models clarify the decision basis and improve interpretability.
- Social value: Coexistence of multiple values is the very goal that many democratic societies should strive for.

- [[Three Types of Pluralistic Models]]
- [[Three types of multidimensional benchmarks]]

Relationship to current alignment and empirical results
- Hypothesis: Standard RLHF can reduce distributive multiplicity.
- Experiment: Comparing the pre-training model with the post-RLHF model in the LLaMA/LLaMA-2/GPT-3 system, the former is closer to the human response distribution (e.g., US, Japan) and has higher entropy.
    - Jensen-Shannon distance is small and average entropy is about 2x.
- Implication: Current methods tend to lose minority opinions and new evaluation and learning methods are needed.

[[RLHF]]は[[分布的多元性]]を減らしてしまうということ<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>

---
This page is auto-translated from [/nishio/A Roadmap to Pluralistic Alignment](https://scrapbox.io/nishio/A Roadmap to Pluralistic Alignment) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
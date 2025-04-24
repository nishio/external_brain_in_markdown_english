---
title: "PFN Automated Prompt Engineering"
---

2023-10-13
[Japanese LLM Benchmarking and Automated Prompt Engineering - Preferred Networks Research & Development](https://tech.preferred.jp/ja/blog/prompt-tuning/)
- [[PFN]] [[Prompt Engineering]] [Automated Prompt Engineering
<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>
This article describes prompt engineering in benchmarking Japanese large-scale language models (LLMs) and methods to automate it. The main points are as follows
- When applying LLM to real tasks, differences in prompts have a significant impact on performance. Prompt template design is important in prompt engineering.
- Even in Japanese LLM benchmarks, the accuracy varies by more than 20 points depending on the prompt template; prompt ingenuity is necessary to get the true performance of LLM.
- Proposed algorithm for prompt optimization. The genetic algorithm is used to sequentially improve the prompt template by crossover and mutation.
- Experimented with Stability AI's Japanese LLM benchmark (JCommonSenseQA). Prompt optimization achieved significant accuracy improvement of up to about 50 points for each LLM.
- Characteristics of optimized prompt templates included placing questions in the second half, clearly communicating the intent of the choices, etc. Each LLM has its own optimal prompt characteristics.
- Prompt tuning is important for improving LLM performance and can be automated. On the other hand, since benchmarks are sensitive to prompts, a fair comparison among LLMs needs to consider the impact of prompts.
As described above, the study showed that automatic optimization of prompts can significantly improve the accuracy of Japanese LLM benchmarks. We believe this is an interesting study that reveals the importance of automation techniques in prompt engineering and the significant impact of prompts on benchmark evaluation.

---
This page is auto-translated from [/nishio/PFN自動プロンプトエンジニアリング](https://scrapbox.io/nishio/PFN自動プロンプトエンジニアリング) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
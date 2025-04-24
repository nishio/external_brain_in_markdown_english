---
title: "ParsuaBot"
---

[2407.03585 Zero-shot Persuasive Chatbots with LLM-Generated Strategies and Information Retrieval](https://arxiv.org/abs/2407.03585?utm_source=chatgpt.com)
- EMNLP 2024: [https://aclanthology.org/2024.findings-emnlp.656.pdf](https://aclanthology.org/2024.findings-emnlp.656.pdf)

<img src='https://scrapbox.io/api/pages/nishio-en/o3/icon' alt='o3.icon' height="19.5"/>
Architecture (Strategy Maintenance Module, SMM)
- LLM Response Generation
    - The user inputs and task instructions are given, and the GPT-3.5 equivalent model is made to issue "bare-bones" persuasion messages.
- Strategy Segmentation & Extraction
    - Contextually segment the generated text and have the LLM self-label the persuasion strategies used by each segment (e.g., impact emphasis, benefit presentation, empathy statement, etc.). Dynamically generated rather than fixed list.
- Fact-checking + IR reinforcement
    - Verify the claims of each segment. For those that are not supported, external searches are used to obtain reliable facts and replace them. This removes halucination while maintaining the persuasion structure.
- Merge & Output
    - The returned factual information is embedded in each strategy section and integrated into a single natural response.

Key point: Because strategy and language content are handled separately, it is possible to automatically determine which claims should be factually reinforced.

The same pipeline works for the three domains of donation solicitation, travel recommendation, and health intervention, and no task-specific data or additional fine-tuning is required.
- The average persuasion score was +0.6 points higher than the previous method for all 3 domains x 2 types of users (cooperative / skeptical).
    - (Persuasion score is a 5-point Likert 1 = not at all persuasive ... 5 = very persuasive, based on actual interaction with 80 crowd workers, one time per person).

---
This page is auto-translated from [/nishio/ParsuaBot](https://scrapbox.io/nishio/ParsuaBot) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
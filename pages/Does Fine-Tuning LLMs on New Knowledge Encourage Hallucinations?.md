---
title: "Does Fine-Tuning LLMs on New Knowledge Encourage Hallucinations?"
---

> [hillbig](https://x.com/hillbig/status/1792334744522485954) When new knowledge is introduced to LLM using fine tuning, performance deteriorates as knowledge acquired during pre-training is also halucinated. This is because it takes time to acquire knowledge that was not known at the time of prior learning and overlearning occurs when it is referenced multiple times. It is effective to use fine tuning to extract knowledge that was learned during prior learning but is not yet usable.
>  Therefore, during fine tuning, it is useful to filter out data that the model does not know and to label it as "this is unknown information".
>  The current AI model does not solve the problem of slow learning in the end and the inability to acquire new knowledge/memory without affecting existing knowledge/memory. There must be a way because people can learn fast and not let new learning results interfere with the existing. It seems to me that there is not yet a mechanism like memory consolidation (CONSOLIDATION).
>  [https://arxiv.org/abs/2405.05904](https://arxiv.org/abs/2405.05904)

---
This page is auto-translated from [/nishio/Does Fine-Tuning LLMs on New Knowledge Encourage Hallucinations?](https://scrapbox.io/nishio/Does Fine-Tuning LLMs on New Knowledge Encourage Hallucinations?) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
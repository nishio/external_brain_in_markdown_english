---
title: "Long-term Dialogue Agent"
---

Hello Again! LLM-powered Personalized Agent for Long-term Dialogue
[https://arxiv.org/abs/2406.05925#:~:text=the%20Long,Agent%20are](https://arxiv.org/abs/2406.05925#:~:text=the%20Long,Agent%20are)
![image](https://gyazo.com/9ae1d031a99e3fb473113497f9842c29/thumb/1000)

<img src='https://scrapbox.io/api/pages/nishio-en/DR/icon' alt='DR.icon' height="19.5"/>
[[LD-Agent]] (Li et al., NAACL 2025): A model-independent framework named Long-term Dialogue Agent, characterized by the separation of event memory and personality information. It consists of (1) a long-term memory that stores the entire past session, (2) a short-term memory of the current session, (3) dynamic personality models of users and agents themselves, and (4) a response generation module. After each session, important events are stored in the long-term memory as summary entries, and new user information is updated in the personality profile. In addition, topic-based memory retrieval is introduced during retrieval to effectively extract past episodes that are relevant to the topic. For example, in a dialogue about hobbies, noise is reduced by narrowing the search to memories in the hobby category. LD-Agent can be applied independently of model size and dialogue domain, and experiments have shown that it can be used on multiple datasets, including PersonaChat-derived Experiments have shown its versatility and effectiveness on multiple datasets, including multi-session dialogues derived from PersonaChat.
---
This page is auto-translated from [/nishio/Long-term Dialogue Agent](https://scrapbox.io/nishio/Long-term Dialogue Agent) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
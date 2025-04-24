---
title: "MemoryBank"
---

[https://ar5iv.labs.arxiv.org/html/2305.10250](https://ar5iv.labs.arxiv.org/html/2305.10250)

<img src='https://scrapbox.io/api/pages/nishio-en/DR/icon' alt='DR.icon' height="19.5"/>
MemoryBank (Zhong et al., arXiv 2023): A long-term memory mechanism designed for LLM. It stores information such as full texts and summaries of past conversations and the user's personality (preferences and personalities) in a "memory bank," and retrieves and refers to related memories during a dialogue. The feature is dynamic memory updating based on [[Ebbinghaus' forgetting curve]] theory, which increases or decreases the intensity of memory according to the passage of time and the degree of importance. Specifically, each memory item is assigned a "strength based on frequency of use," and memories that are not referenced for a long period of time decay in strength and are forgotten like humans, while memories that are recalled even once are strengthened and their lifespan is prolonged.
- This is interesting.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
    - Even this external brain is being maintained to make it easier to take miscellaneous notes first and then refer to it again after a while.
    - This idea itself referred to the behavior of the hippocampus

MemoryBank can be externally attached to existing models such as ChatGPT, and was incorporated into SiliconFriend, a long-term interactive bot, as an example of implementation. SiliconFriend was evaluated in a psychological counseling dialogue model, and showed promise as a companion AI for long-term human interaction, being able to appropriately recall past events while empathizing with the user's emotions.
---
This page is auto-translated from [/nishio/MemoryBank](https://scrapbox.io/nishio/MemoryBank) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
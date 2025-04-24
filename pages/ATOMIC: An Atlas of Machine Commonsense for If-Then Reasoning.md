---
title: "ATOMIC: An Atlas of Machine Commonsense for If-Then Reasoning"
---

![image](https://gyazo.com/67da5e404b24e59a97ceee35850e8fb7/thumb/1000)
[https://arxiv.org/abs/1811.00146](https://arxiv.org/abs/1811.00146)
<img src='https://scrapbox.io/api/pages/nishio-en/o3-mini-high/icon' alt='o3-mini-high.icon' height="19.5"/>
[[ATOMIC]] is a [[knowledge graph]] that collects a large amount of causal and inferential common sense knowledge about everyday events. The main points are as follows

- Large Data: Over 877,000 "if-then" relationships (e.g., "If X gives Y a compliment, Y will give a compliment in return") are collected as natural language text.
- Multidimensional Reasoning: 9 if-then inference types, including "intention," "reaction," "necessary preconditions," and "subsequent action" to an event, allow inference from various aspects such as cause, effect, psychological state, and person attributes.
- Use of Hierarchical Structures: These inference types are organized in hierarchical structures such as causality (cause and effect) and object (subject and recipient of action) and are used for learning in neural networks.
- Neural generative model: Proposes a sequence generative model that takes events as input and generates relevant inferences (e.g., presupposed events, subsequent reactions, etc.), using pre-trained representations such as GloVe and ELMo, trained with an encoder-decoder model. The model is trained on an encoder-decoder model.
- Evaluation Results: BLEU scores and human evaluation showed that taking advantage of the hierarchical structure of if-then relationships in multi-task learning improves the accuracy of inference over single-task models.
- Differences from Existing Knowledge Graphs: While traditional knowledge graphs such as ConceptNet are primarily categorical, ATOMIC contains a wealth of causal inference information derived from specific everyday events, with approximately 75% or more of the knowledge being new knowledge.

In this way, ATOMIC aims to contribute to improved AI understanding and response generation as a large-scale, multi-dimensional resource for machine common sense reasoning about everyday events.
---
This page is auto-translated from [/nishio/ATOMIC: An Atlas of Machine Commonsense for If-Then Reasoning](https://scrapbox.io/nishio/ATOMIC: An Atlas of Machine Commonsense for If-Then Reasoning) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
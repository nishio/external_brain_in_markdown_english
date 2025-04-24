---
title: "Reflective Memory Management"
---

[[In Prospect and Retrospect: Reflective Memory Management for Long-term Personalized Dialogue Agents]]
[https://arxiv.org/pdf/2503.08026](https://arxiv.org/pdf/2503.08026)
<img src='https://scrapbox.io/api/pages/nishio-en/GPT-4.5/icon' alt='GPT-4.5.icon' height="19.5"/>
# summary of thesis
.
Reflective Memory Management (RMM, [[Reflective Memory Management]]) is a new memory management method for accurately remembering and using past information to sustain conversations with users over a long period of time:

- Prospective Reflection.
- After the conversation is over, the content of the dialogue is broken down and summarized in topic units and organized as a semantically coherent memory. This prevents fragmentation of memory by fixed units (turns, sessions, etc.).

- Retrospective Reflection.
- During conversation generation, LLM itself automatically evaluates "which memories were useful". This evaluation is used as a reward for reinforcement learning to improve and adjust memory retrieval results online.

# Issues with conventional methods
.
- Fixed granularity memory management: Fixed delimitations in terms of turns and sessions do not capture semantic coherence, and memory becomes fragmented and incomplete.
- Fixed memory retrieval method: Cannot respond to diversity of users and interaction situations.

# Advantages of the proposed method (RMM)
- Topic-based memory management improves the accuracy of memory retrieval by preserving semantic coherence.
- The accuracy of memory retrieval can be improved online without labeling data by allowing the LLM itself to determine the degree of usefulness of the retrieved memories.

# experimental results
.
- Validated on MSC and LongMemEval datasets.
- The proposed method is more accurate than existing baselines, especially on the LongMemEval dataset, where the percentage of correct responses is more than 10% higher than without memory management.

# Conclusions/future issues
.
- RMM showed excellent accuracy in long-term personalized dialogue agents.
- Future issues include improving computational efficiency, supporting multimodal dialogue, and strengthening the protection of personal information.

---

The above is a compact summary of the main points of the paper.


relevance
- [[MemoChat]]
- Survey [https://chatgpt.com/c/67e139ac-05fc-8011-a6d8-d6887700b11b](https://chatgpt.com/c/67e139ac-05fc-8011-a6d8-d6887700b11b)
    - [[Keep Me Updated]]
    - [[MemoryBank]]

---
This page is auto-translated from [/nishio/Reflective Memory Management](https://scrapbox.io/nishio/Reflective Memory Management) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
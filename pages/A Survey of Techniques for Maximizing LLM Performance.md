---
title: "A Survey of Techniques for Maximizing LLM Performance"
---

[[OpenAI DevDay]]
![image](https://gyazo.com/7d3bf7ea4b4e83d411ea89961a1a5d1a/thumb/1000)
I saw this graph on social media and was curious about the details, so I'm glad it's available on video!

45%→65%
- Baseline was 45%.
- Tried [[HyDE]] first, which did not work for this use case
- We also tried fine tuning the embedding
    - This worked well from an accuracy standpoint, but was too expensive and slow to adopt.
- Chunk size and delimitation method
    - That improved it by 20% to 65%.
    - Not yet at a level where we can give it to our clients.
    - I've done 20 iterations so far.

65%→85%
- [[cross-encoder]] or using a rule-based approach [[reranking]].
    - Example of a rule: Use the latest
    - Significant performance improvement
- Classification.
    - Classified domains and assigned different metadata accordingly
    - It's not explained specifically, but in a Cybozu-like context, for example, it would be something like "this is a schedule, let's give the participants' information" or "this is a space conversation, let's give the thread title and the name of the space".

85%→98%
- Prompt engineering again
- Observe again what questions are failing
    - For example, for questions that require explicit numbers, we stopped extracting them from the documentation and provided a tool to issue SQL.
- query expansion
    - The work was different from what I imagined by the name (I thought it was to give data that is easy to hit on the side of the search target).
    - Split user input into multiple queries, search them in parallel, and return a composite
    - I think this is pretty use case dependent.
- I didn't do fine tuning anywhere, I wanted to emphasize this.


![image](https://gyazo.com/f83febf41f779bc0456dd7f17fe79bda/thumb/1000)
- ![image](https://gyazo.com/e52fe01c9bd451720c21ee19782207b1/thumb/1000)

[https://www.youtube.com/watch?v=ahnGLM-RC1Y](https://www.youtube.com/watch?v=ahnGLM-RC1Y)


---
This page is auto-translated from [/nishio/A Survey of Techniques for Maximizing LLM Performance](https://scrapbox.io/nishio/A Survey of Techniques for Maximizing LLM Performance) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "In-context Autoencoder for Context Compression in a Large Language Model"
---

2307.06945 In-context Autoencoder for Context Compression in a Large Language Model
[https://arxiv.org/abs/2307.06945](https://arxiv.org/abs/2307.06945)
<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>This paper proposes an In-context Autoencoder (ICAE) to solve the context length constraint of Large Language Models (LLMs) ICAE has the following features.
- The power of LLM can be used to compress long contexts into short memory slots.
- Pre-learning with two objective functions, Autoencoding and Language Modeling, allows memory slots to accurately and comprehensively represent the original context.
- After pre-training, fine-tuning with instructional data enhances interaction with the various prompts.
- Based on Llama-7b, 4x context compression with approx. 1% additional parameters. Improved latency and GPU memory cost during inference.
- Provides insight into LLM memorization and suggests a new perspective on the relationship between human working memory and LLM representation learning.
- Suggests potential for further research in context management and can be combined with other long context modeling studies.

ICAE is a simple and scalable approach that addresses the long context problem in LLMs and has the potential to achieve greater compression ratios with more powerful LLMs. Future applications to multimodal LLMs are also expected.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Learn more about the connection between human [[working memory]] and LLM [[representational learning]].

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>ICAE experimental results suggest an interesting link between human working memory and LLM representational learning.
- Memory selectivity
    - In the example of text restoration by ICAE, "large pretrained language model" became "large pretrained model," "The results prove" became "The experimental evidence proves," and so on. The results prove" becomes "The experimental evidence proves", and so on. This is similar to the mistakes humans make when memorizing the same text, suggesting that the model selectively emphasizes or ignores parts of the information based on its own understanding.
- Relationship between amount of knowledge and memorization
    - The more powerful LLMs tend to require less memorization and smaller memorization efforts. This is analogous to human learning, where individuals with extensive knowledge can more easily acquire new information, while individuals with limited knowledge tend to rely on rote memorization.
- Differences in memorization by content type
    - We found that while general text is easy to compress and recover, random text is very difficult to compress and recover. This strongly supports that LLM memorization patterns are very similar to humans.
- Improved memorization capability through prior learning
    - Prior learning in ICAE is thought to improve working memory in LLM. This is analogous to how humans increase memory capacity through extensive memory training, improving the brain's memory-encoding capacity.

These findings provide a new perspective on the link between working memory and LLM representational learning (context window) in cognitive science. Further elucidation of the mechanisms of working memory in LLMs may lead to the development of more efficient and human-like LLMs in the future. LLM findings may also be useful in understanding how human memory works, and exploring the relationship between LLM and human cognition will become increasingly important as an area where AI and cognitive science converge.

---
This page is auto-translated from [/nishio/In-context Autoencoder for Context Compression in a Large Language Model](https://scrapbox.io/nishio/In-context Autoencoder for Context Compression in a Large Language Model) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
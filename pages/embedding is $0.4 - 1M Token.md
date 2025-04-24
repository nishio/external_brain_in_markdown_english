---
title: "embedding is $0.4 / 1M Token"
---

[Pricing](https://openai.com/pricing) [[Embedding API]]
> Model	Usage
>  Ada	$0.0004 / 1K tokens

Roughly speaking, a company with 1,000 employees posting an average of 1,000 words daily to the groupware would pay less than $200 per day for embedding every utterance.

Assuming an average of 10 posts, that's 60MB of vector indexes created per day, so Pinecore's pay-as-you-go fee is $0.05, or about $1,000 in running costs.

[New and improved embedding model](https://openai.com/blog/new-and-improved-embedding-model)
2022-12-15 `text-embedding-ada-002` is best
- context length: 8192
- 1536 dimensions
    - They made it 1/8th the size, but they still got more talent.

[OpenAI API:what-are-embeddings](https://platform.openai.com/docs/guides/embeddings/what-are-embeddings)
- [[cl100k_base]] is the name of the tokenizer
    - > For second-generation embedding models like text-embedding-ada-002, use the cl100k_base encoding.
    - [[tiktoken]]
- [[Pinecore]]

---
This page is auto-translated from [/nishio/embeddingは$0.4 / 1M Token](https://scrapbox.io/nishio/embeddingは$0.4 / 1M Token) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
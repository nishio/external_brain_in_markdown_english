---
title: "Why do you use a space for line breaks before Embedding?"
---

The sample code at [OpenAI API](https://platform.openai.com/docs/guides/embeddings/what-are-embeddings) says this
python

```
def get_embedding(text, model="text-embedding-ada-002"):
   text = text.replace("\n", " ")
   return openai.Embedding.create(input = [text], model=model)['data'][0]['embedding']
```


Why is replacement necessary when whitespace and line breaks themselves are different tokens? Is it really necessary? I was skeptical, but I found a statement that it was because the replacement would improve the result.
- > Replace newlines with a single space
- >  Unless you're embedding code, we suggest replacing newlines (\n) in your input with a single space, as we have observed inferior results when newlines are present.
    - [How to generate embeddings with Azure OpenAI Service - Azure OpenAI | Microsoft Learn](https://learn.microsoft.com/en-us/azure/cognitive-services/openai/how-to/embeddings?tabs=console)

No follow-up exam.
- I doubt if it's the same in Japanese.
- but I'm inclined to follow it.

[[OpenAI API]]

---
This page is auto-translated from [/nishio/Embedding前に改行をスペースにするのはなぜ？](https://scrapbox.io/nishio/Embedding前に改行をスペースにするのはなぜ？) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "GPT3 reverses the information density."
---

2023-02-28
![image](https://gyazo.com/14e4f77793d723af030402d9042df1bf/thumb/1000)
![image](https://gyazo.com/10c1b8c1b9b9b1817d78f1133a748f82/thumb/1000)![image](https://gyazo.com/9f52e93ff88b586b14311c82d230a8b8/thumb/1000)
![image](https://gyazo.com/f0a0af30d47e17bf5cebf9d79774f2b6/thumb/1000)![image](https://gyazo.com/b5be2d6f88a06f83777451a77264327b/thumb/1000)
[OpenAI API: Tokenizer](https://platform.openai.com/tokenizer)

The [[tokenizer]] in [[GPT3]] often carves a single Kanji character into multiple tokens.
- This is an unfavorable situation for the Japanese.

Until now, Chinese and Japanese who use Chinese characters had a higher density of information to input than those who use the alphabet.
- English took up about twice the area of writing the same content in Japanese and English.
- The size of a person's physical field of vision doesn't vary much by race.
- Therefore, the Japanese had an advantage over Westerners in that the amount of information they could input through their eyes at once was twice as large as that of Westerners.

However, from the GPT3 perspective, if the same content is given in English and Japanese, the number of tokens in Japanese is approximately two to three times larger than in English.
- GPT3 can input about 4000 tokens at a time.
    - This is what human physical vision looks like
- In other words, for GPT3, the amount of Japanese-language written at a time is small.
- It is widely used to pass contextual information to ChatGPT, saying "Reply with this", but in this case, you can pass 2-3 times more context if you pass it in English, the difference is huge!

token-metered billing

There is talk that the accuracy of [[Semantic Search]] is not good enough for Japanese.
- Kanji characters are split up, so kanji that are close together in the character code table are considered to have "1/2 or 2/3 of a token in common."
- Well, that's a lot of hurdles to overcome to make it work.

Q: Is the tokenizer naively tokenizing each byte?
- A: It's not that simple.
- The highlight is the fact that "information" is one token.
    - ![image](https://gyazo.com/b5be2d6f88a06f83777451a77264327b/thumb/1000)
    - It doesn't matter how many bytes the original is, it doesn't interfere with making it into a single token.
    - If you look closely, you can see why there are nine tokens for the four Chinese characters, except for "報", which is two tokens, and "報", which is three tokens.
- So why are the three bytes that make up "emotion" inscribed on two tokens?
    - If the input is chopped naively into bytes, there are less than 70 different tokens.
    - However, chopping into small pieces causes the "narrowing of the field of vision" phenomenon described above, so frequently occurring byte sequences are stacked together to make a single token with multiple bytes.
    - This "frequently used" part depends on the corpus you are assuming.
    - GPT3 is not specific to Japanese, so the frequency of occurrence of "emotion" is much lower than that of "information".
    - So the state is deemed not worthy of being made into one token.
- Currently there are about 5,000 different GPT3 tokens in total.
    - Increasing the number is technically not a problem, but the more you increase it, the more it costs to learn.
    - For economic reasons, there are few resources to devote to a minority language such as Japanese.

PS
> [@kitar](https://twitter.com/kitar/status/1633426489390809088): maybe ChatGPT's tokenizer is improved over GPT3...? I was just trying to calculate it with tiktoken,
> text: information density
> text-davinci-003: 9 tokens
> gpt-3.5-turbo: 4 tokens
>  and came out.

python

```
In [10]: tiktoken.encoding_for_model("gpt-3.5-turbo")
Out[10]: <Encoding 'cl100k_base'>

In [11]: tiktoken.encoding_for_model("text-davinci-003")
Out[11]: <Encoding 'p50k_base'>
```

Okay, it's definitely different.
No, this is not new with ChatGPT API.
- They're also using a new tokenizer in the December 2022 [New and improved embedding model](https://openai.com/blog/new-and-improved-embedding-model).
- ![image](https://gyazo.com/ff6822187c0b6d035c4d7595edc1adf2/thumb/1000)
    - [https://platform.openai.com/docs/guides/embeddings/what-are-embeddings](https://platform.openai.com/docs/guides/embeddings/what-are-embeddings)
- If [cl100k_base
python

```
In [12]: tiktoken.get_encoding("cl100k_base").encode("information density")
Out[12]: [40474, 78943, 28741, 27479]
```

    - 4 tokens.
- That the demo on [https://platform.openai.com/tokenizer](https://platform.openai.com/tokenizer) uses V1 GPT-3.

---
This page is auto-translated from [/nishio/GPT3では情報密度が逆転する](https://scrapbox.io/nishio/GPT3では情報密度が逆転する) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
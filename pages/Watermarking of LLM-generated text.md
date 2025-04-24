---
title: "Watermarking of LLM-generated text"
---

I didn't know you could do that.

> [@hillbig](https://twitter.com/hillbig/status/1683969478235914240?s=20): a method of [[watermarking]] the generated text of [[LLM]]. Based on the hash value calculated from the previous token and the random number generation seed, when generating the next token, the candidate tokens are divided into green set (G) and red set (R), and the logit of the generation probability of the token belonging to G is increased by a constant amount. Sentences generated in this way have a much higher percentage of tokens belonging to G than general sentences, which can be examined to see if they were generated.
>  Since only the immediately preceding token is dependent, it is possible to detect a generated sentence even if it is cut off in the middle of a sentence. In addition, since a constant is added to the logit, tokens with low entropy are not changed and tokens with high entropy are changed, thus minimizing quality deterioration of the generated text. This constant can be changed according to the situation (usage or user), allowing the strength of the watermark to be changed dynamically.
>  Even if the method is disclosed, it is difficult for an attacker to remove the watermark as long as the random number species at the time of generation is hidden.
>  This approach itself can be used for generative models in general, not just LLMs.
>  One of the best papers of ICML 2023
>  Note that some such watermarks are probably already in place in commercial services.
>  [A Watermark for Large Language Models | OpenReview](https://openreview.net/forum?id=aX8ig9X2a7)

[[Watermark]]

---
This page is auto-translated from [/nishio/LLM生成テキストの透かし](https://scrapbox.io/nishio/LLM生成テキストの透かし) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
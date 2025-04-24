---
title: "Is a Japanese language model necessary?"
---

Talk about "another small model" being futile, but "a tokenizer plus an extra layer suitable for Japanese" is necessary.

from  [[Unexplored Conference 2023]]
Is a Japanese language model necessary?
[https://twitter.com/nishio/status/1634236182136762368](https://twitter.com/nishio/status/1634236182136762368)
- <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>Is a Japanese language model necessary?
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>However, if the efficiency of communication in Japanese with a giant language model is lower than that in English, it is a loss for Japanese speakers, so there is no need to do anything.
- <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>Are you asking me to increase the number of Japanese language study data?
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>No, different language speakers have conflicting interests because tokenizer token splits follow the frequency of occurrence of words in the language. One model with more data is not good enough.
- <img src='https://scrapbox.io/api/pages/nishio-en/human/icon' alt='human.icon' height="19.5"/>If machine translation evolves, it won't matter.
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>If the English word sequence is then converted to a Japanese word sequence, the resolution of the world by the English language will be lower to match the English language in a lower domain than the Japanese language, so the language can only be inferior to the English language.

@kuboon
I think I heard something about recent machine translation being converted once into an intermediate language that is not any language, like LLVM for natural languages.
@nishio
What humans imagine by the term "intermediate language" is a sequence of "discrete symbols" called words, but in the first place, in LLM, what corresponds to a single word is a vector with a float of 1000 dimensions or so, and its expressive power is an order of magnitude higher. Therefore, it is necessary to "directly convert it into Japanese" rather than "convert it into English and then into Japanese.
@kuboon
I was envisioning machine translation directly from a float 1000 dimensional word sequence into natural language, without output from LLM into English.
@nishio
If it is necessary and the accuracy there is inferior for a certain natural language, only the speakers of that language will suffer a loss. This is not a problem that can be solved by leaving it to the speakers of other languages, since there are conflicting interests among the speakers of each language.
@kuboon
Would it be good if there was a mechanism to standardize the tokenizer API so that native speakers of each language could commit to it?
@nishio
The tokenizer alone is too thin. It's just a discrete token ID of a sequence of bytes. I think we need an opening that can I/O information around that token ID becoming a vector, and then going a little further inward, where the superficial differences in language disappear and it becomes a vector of meaning.

relevance
    - [[Do differences in Japanese Tokenizer affect downstream task performance?]]
    - Morphological analysis improves performance.

---
This page is auto-translated from [/nishio/日本語の言語モデルは必要か？](https://scrapbox.io/nishio/日本語の言語モデルは必要か？) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
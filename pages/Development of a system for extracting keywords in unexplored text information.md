---
title: "Development of a system for extracting keywords in unexplored text information"
---

![image](https://gyazo.com/a831f1084705e301961a387aa11c260c/thumb/1000)
- ![image](https://gyazo.com/e05f0c4fc08899f9df304c19cd4bfaf1/thumb/1000)![image](https://gyazo.com/643756b0b3e9c062d3ad48453cbe2717/thumb/1000)


[PDF](https://www.ipa.go.jp/files/000005543.pdf)

- The concept of [concentration (of one's attention)
- Number of sentences in which the string appears twice ÷ Number of sentences in which the string appears once
- Probability of two or more occurrences of a string conditional on the string occurring once
    - If a string occurs according to the [[Poisson distribution]], it matches the word frequency.
    - Actual substrings are more widely distributed.
    - The distribution of human-determined keywords is concentrated in that part of the market.

score
- The "number of sentences in which the string appears once" is in essence [[DF]], so dividing by this is [[IDF]].
- In [[tf-idf]], the numerator is tf, but here we have DF2
- If df2 is less than 3, the logarithmic score is set to -10000
- If the score exceeds 0.5, saturate it with 0.5.

Applications [QuickSolution - Wikipedia](https://ja.wikipedia.org/wiki/QuickSolution)

This can be interpreted as a function that takes a string as an argument and returns a "keyword-like" value
- Not "[Keyword character representative of this document.
- It is "the key word character in this language."
- This function must be obtained from a large corpus in advance
    - In what form should it be preserved?
    - Sufficient information in the form of suffix array, but overly detailed
        - Just the number of occurrences in different sentences, and it is enough to know if it is 0, 1, or 2 or more.

Attributing keyword extraction to the problem of [word segmentation
- The problem of finding the division that maximizes the product of the scores of each of the divided strings
    - Since the score is less than 1, it is better not to split if the score is the same
    - Why? Because substrings of the → keywords also score high.
- I think the structure would be mathematically similar to [[SentencePiece]].
    - see  [[SentencePiece unigram language model]]
    - The "keywordiness" score reads "wordiness."
        - Find the [[word segmentation]] with the maximum likelihood using the [Viterbi algorithm

After splitting, keywords are those that satisfy the following conditions
- Frequency ranges from 0.00005 to 0.1
- Logarithmic score greater than -1
- Length 2 or more

[[Suffix Array]]
- [[keyword extraction]]
- [[suffix array]]

---
This page is auto-translated from [/nishio/未踏テキスト情報中のキーワードの抽出システム開発](https://scrapbox.io/nishio/未踏テキスト情報中のキーワードの抽出システム開発) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
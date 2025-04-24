---
title: "Creating a candidate set of key phrases"
---

- In [[keyphrase extraction]], the question is how to make candidates
- [[RAKE]] chops the stop word as a delimiter.
- [[TextRank]] first filters out all but nouns and adjectives
    - [[Phrase-based TF-IDF]] uses only the longest noun phrase
- All substrings are candidates.
        - [[Development of a system for extracting keywords in unexplored text information]]
- I want to include strings enclosed in parentheses as keyword candidates.

- When trying to find key phrases with an approach that calculates scores for the candidates and takes the big ones
    - [[EmbedRank]] uses similarity to the original document, so the text itself must not be included in the candidates.


---
This page is auto-translated from [/nishio/キーフレーズ候補集合の作成](https://scrapbox.io/nishio/キーフレーズ候補集合の作成) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
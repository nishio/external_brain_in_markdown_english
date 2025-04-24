---
title: "Embedded vectors good or bad"
---

- What makes an [[embedded vector]] good or bad?

For two words that are close together
- Identical: B to A (Python and Pyth0n) → Replace B in original data with A
- Synonyms: A and B mean the same thing (please see below) → Keep the original data, but unify the mapping between words and IDs.
- synonym: [[quasi-synonym (word that has a similar meaning to another, but is not interchangeable)]] → this is OK as is
- Antonyms: A and B are [[antonyms]] → add 1 axis for antonyms to the vector and swing +1/-1 as appropriate
- Concatenation: A and B are a single meaning in the form "AB" → need to add vocabulary, be creative when reading input

Teaching conjunction increases vocabulary. Teaching the same decreases it.
This teacher data itself can be reused.

I need to make some modifications to the learning process, I want to use vectors around, and in the end I need to create my own [[word2vec]]-like system?

- [[Good or bad dispersion representation]]
- [[distributed representation]]

---
This page is auto-translated from [/nishio/埋め込みベクトルの良し悪し](https://scrapbox.io/nishio/埋め込みベクトルの良し悪し) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "rare symbol"
---

![image](https://gyazo.com/88ea646dde0a8b6a91f7ab66efd59077/thumb/1000)

- It is often the case that [[unknown language]], etc. with a frequency of zero occurrences are grouped into unknown symbols such as <unknown>.
    - And there's not much better way to do it.
- However, words that appear only twice in the training data are also rather disturbing.
    - If you simply replace it with one symbol as a rare word, that makes me feel like I'm throwing away information.
- approach
    - divide into clusters
        - Not always mechanically separated, e.g. humans separate "hiragana, katakana, kanji".
    - attribute
        - Unlike clusters, it is not exclusionary.
        - Expressed as a bundle of attributes, such as "is wood-biased," "is a regular kanji character," etc.
    - Embed using methods such as [skip-gram

---
This page is auto-translated from [/nishio/レアシンボル](https://scrapbox.io/nishio/レアシンボル) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
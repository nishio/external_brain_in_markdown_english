---
title: "reverse search"
---

- The usual [[search (e.g. for someone using a search engine)]] is an operation that performs some computation on a set of documents D using the query q and returns the result
    - That is, $f(D_i, q) \to \mathbb{R}$
    - naively, "1 if document Di contains q"
    - It is often done by returning some kind of score and displaying them in order of highest to lowest.
    - Conversations on [[chatbot]] are searched in response to the user's utterances (example implementation)
    - The $(q_i, D_i)$ is prepared in advance and $f(P, q_i)\to\mathbb{R}$ is computed for the user's utterance P.
![image](https://gyazo.com/a922705525c443d0c9f1d163a0b00001/thumb/1000)
- [Scrapbox
    - Left ordered search if you interpret explicit bracketing of links as an input to the search query.
    - If you do "Automatically link when a link title that has already appeared", the page will be P and the link title set will be q reverse search
---
This page is auto-translated from [/nishio/逆検索](https://scrapbox.io/nishio/逆検索) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
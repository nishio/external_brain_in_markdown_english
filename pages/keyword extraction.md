---
title: "keyword extraction"
---

- Related: [[keyphrase extraction]].
    - This word is used when we are very conscious of not stopping at one word.
    - I'd like to see "100 Personnel Systems for 100 People" or "Evaluating by Harmony, Generalists are Chosen."
    - Even the world's "key phrase extraction" is often subject to restrictions such as "noun sequence" or "`adjective*noun+` form"
            - [[noun phrase approach]]
        - It's not possible to extract key phrases like the above with such a constrained method.
            - [[Key phrases that allow verbs]]
            - [[Active bracketing of verbs]]
    - Often there are times when you want to use a string of characters that do not appear in a sentence as a key phrase.
        - I want them to be connected by an "information sharing" link when the phrases "information sharing" and "sharing information" are used.
            - [[I'd like to associate "information sharing" with "information sharing."]]
            - [[Key phrases that do not appear in the sentence]]

technique
- An approach that does not use linguistic knowledge
    - Simple [[word frequency]].
            - Need for [stopword
        - Throwing away information on word order.
            - The "General Manager's Association" issue where the idiom is split.
        - Synonyms are considered different
        - [[cooccurrence]]
        - co-location
            - N-grams, etc.
            - intra-window co-occurrence
        - intra-document cooccurrence
                - [[concentration (of one's attention)]]
    - [[tf-idf]]
        - Approach to map real-valued scores whereas the stop word was 0/1.
        - 'The less frequently it appears in other texts, the more appropriate it is to characterize this text.'
            - [[IDF]] part
        - Frequent occurrence as a word, but sometimes an important key phrase in the form of an idiom
    - [[RAKE]]
- graph based (e.g. graph)
    - Graph word adjacencies and choose the one with the highest rank.
    - Use PageRank
        - [[TextRank]]

---
This page is auto-translated from [/nishio/キーワード抽出](https://scrapbox.io/nishio/キーワード抽出) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Phrase-based TF-IDF: Application of Noun Phrase Analysis"
---

    - [[Phrase-based TF-IDF]] : Application of [NPP
    - [[tf-idf]]
        - [[keyphrase extraction]]
        - [[Yugo Murawaki]]
    - Abstract Recognition of key words in a document is a fundamental task for many applications. Such words are often not words but word sequences. However, state-of-the-art unsupervised methods score words by summing TF-IDFs and do not recognize the semantic cohesion of word sequences. In this paper, we propose a method to calculate TF-IDFs directly for phrases consisting of multiple words by applying the internal structure analysis of noun phrases, and investigate its behavior.

- [[Conundrums in Unsupervised Keyphrase Extraction]] showed that word-based [[TF-IDF]] is stronger than methods such as [TextRank
    - [[Word-based TF-IDF]] defines the phrase score as the sum of the TF-IDFs of the component words
    - In addition to that, the heuristics of limiting to the longest noun phrase is unconsciously used
    - This avoids the [[grammaticality]] problem.

- unithood
    - “the degree of strength or stability of syntagmatic combinations or collocations”
        - Degree to which the word sequence functions as a cohesive entity
- termhood
    - “the degree that a linguistic unit is related to (or more straightforwardly, represents) domain-specific concepts”
        - Degree to which a word sequence is associated with a particular concept.
- The word-based TF-IDF is
    - > $\mathrm{tfidfW}(w) = \mathrm{tf}(w) \times log(D/D_w)$
        - where tf is the frequency of occurrence of the word wi in sentences, D is the number of all sentences, and $D_{w_i}$ is the number of sentences containing the word wi
    - > $\mathrm{term}(p) = \sum_{w \in p} \mathrm{tfidfW}(w)$
        - p: phrase
    - > $\mathrm{unit}(p) = (p\in\mathrm{longest(doc)) ? 1 : 0}$
        - longest is the longest noun phrase
    - > $\mathrm{tfidf(p)} = \mathrm{unit}(p) \times \mathrm{term}(p)$
- For the definition of UNIT, only whether it is the longest noun phrase is used.
    - If we were to include all the subword strings of the longest noun phrase
        - > $\mathrm{unit}(p) = (p\in\mathrm{all(doc)) ? 1 : 0}$
        - Effective in raising the upper bound of Recall, but overall worsened accuracy.
        - This means that unit = 1 is not good, even for inappropriate partial noun phrases.
        - Then give the appropriate score for the partial noun phrase

This approach improves accuracy for longer sentences.
Not improved for short sentences

[https://ipsj.ixsq.nii.ac.jp/ej/?action=repository_action_common_download&item_id=95866&item_no=1&attribute_id=1&file_no=1](https://ipsj.ixsq.nii.ac.jp/ej/?action=repository_action_common_download&item_id=95866&item_no=1&attribute_id=1&file_no=1)

---
This page is auto-translated from [/nishio/フレーズベースTF-IDF: 名詞句解析の応用](https://scrapbox.io/nishio/フレーズベースTF-IDF: 名詞句解析の応用) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
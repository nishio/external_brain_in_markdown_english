---
title: "Auto Bracketing"
---

2019-03-21
Auto-bracketing is not a good idea because if you generate a lot of low-quality links, they will be [[suggested]] only by garbage and "[[making a house into a garbage dump]]" will occur. It is true that [[keyword extraction]] on each page and making it into a link would be a disaster. But that is a problem of "low quality," not of automation. What is [[quality of links]]?

Consider a bad example
- For example, let's say each page of a book is a Scrapbox page.
    - If a certain keyword X appears 100 times, it's not appropriate to make it a link all the time.
        - ![image](https://gyazo.com/04ed3f1e6635b34079512d12170502d5/thumb/1000)
        - If you see a hundred links, it's just "Wow, that's a lot of links.
        - Then it would still be better to present only the information, "You will find that keyword in book A.
        - This is [[Examples of unexpected discoveries in searches]].
            - A keyword is unexpectedly presented as being included in a certain book and feels valuable
            - You can open the book and search again to see which specific page in the book it is on.
        - There is no straightforward way to achieve this on Scrapbox.
            - For example, if each page has a "book ID (name or ISBN)", you can use the ID and a set of keywords to narrow down the search within a book.
            - If we try to achieve this with a link, we would need a link that expresses "the occurrence of keyword X in book A".

Narrow links are useful
- In other words, "links that appear infrequently in other text" are useful
    - On the other hand, my most linked in Scrapbox is the `KJ method` and the `Engineer's Intellectual Production Method`.
        - Words related to the content of interest are naturally frequent.
        - The dilemma of choosing something that simply appears infrequently is to choose something that is "uninteresting".

- Similar concept to [IDF
    - If all links are equivalent, then it is a function of IDF
        - In fact, the links are not equivalent.
            - The same "five times" but these are different in usefulness.
            - ![image](https://gyazo.com/0a94b11c8751580c06fe7914c76756f8/thumb/1000)

- Links between distant objects are beneficial.
    - So there is "near" and "far" as a relationship between pages
        - How is this defined?
            - [[Page proximity]]

    - What is [[Page proximity]]?
    - Pages belonging to the same chapter are close pages
        - This should give the chapter structure as metadata
    - Pages belonging to the same author's book are close pages
    - Book > Chapter > Section ... Hierarchical Structure
    - When the lower structure contains keywords, the upper structure also contains keywords.
        - This has a [[pooling]] feel to it.
        - Hierarchical structure is a good fit for Given
            - A keyword that appears five times in the same book is different from a keyword that appears five times in the same chapter or five times across chapters.
                - [[pooling]] Then the former would be one time and the latter five times.
            - Higher IDFs in higher tiers are more valuable.
    - What if the hierarchical structure is not Given?
        - Assuming a book, adjacent pages are close pages
        - Pages with similar content (= many keywords in common) are close pages
        - Hierarchical structures can be created by [[Agglomerative Hierarchical Clustering]].

![image](https://gyazo.com/b60143d3354814ea817ad015c51b3cc9/thumb/1000)

    - [[Proximity is determined by search]] Can't you?
    - [[nodal point of thought 2019-02-18#5c6a9ccfaff09e00004ee473]] as it relates to
- Bonus if the link already exists in Scrapbox
- I want it to be able to run incrementally.
- I hope it can be improved incrementally.

    - [[Nodes of Thought2019-03-21]]

---
This page is auto-translated from [/nishio/自動ブラケティング](https://scrapbox.io/nishio/自動ブラケティング) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
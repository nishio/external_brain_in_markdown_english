---
title: "link suggestion"
---

![image](https://gyazo.com/ae2fa8e23ef50298e6ba7a6f16a7a028/thumb/1000)
- Isn't keyphrase extraction what is needed?
- Maybe we need a "link suggestion" so to speak?
    - Document set and one new document entered
    - Output "link by common keyphrase" from new document to document set
- difference
    - keyphrase extraction
        - given a document
        - A short string is obtained.
        - We call this short string a "key phrase.
        - You may create links after the fact between documents where keyphrases are common, but you don't care about that at the keyphrase extraction stage.
    - link suggestion
            - The main purpose is to suggest [[link]].
        - The set of documents to be linked is given from the beginning
        - Score links based on their usefulness as links, rather than scoring key phrases
            - For example, a link with a very high number of occurrences is not useful and will score lower.
                - This depends on the use case.
- The "occurrence" of "join if it occurs twice" in [[RAKE]] can be interpreted as extending to a set of documents, not just a new document.


relevance
    - [[Interactive keyword generation]]
    - For example, in the chat interactive use case, "logs" correspond to "existing documents".
        - We don't just look at the latest posts and extract key phrases.
    - Use case to suggest links from a newly written document to a document stored in Scrapbox
    - I noticed this when I was making [[Scrapbox Keyphrase Suggestions]].

---
This page is auto-translated from [/nishio/リンクサジェスト](https://scrapbox.io/nishio/リンクサジェスト) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
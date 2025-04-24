---
title: "Scrapbox Englishization Plan"
---

2019-03-21 [[Multilingual development based on machine-friendly English]] reminded me of this article
- Over there, we're talking about creating editions in different languages based on the English version.
- If you put the original text at the end, you don't have to worry so much about translation errors.
- If you don't understand, read below.
---
After about 10 months, I reconsidered.
- Translated on Scrapbox does not need to be served
- Spit out HTML from JSON in Scrapbox
- How about md5digest for the page title?
    - English Title
    - English text
    - ---
    - Automatic translation from Japanese
-----
2018−04
    - [[English Transmission Support]]
- I know in my head that it is better to transmit in English.
    - but not much motivation to pay the additional cost unless the need is immediate.
- What you write in Scrapbox should be automatically translated into English and reprinted by Google Translate
- But Scrapbox's API seems to be too cumbersome to achieve sequential updates.
- As a small start, you could first export it in JSON, translate it, and import it.
- Insert `(auto-translated from [Japanese http://....])' in the first line? and insert `(auto-translated from [[Japanese959596]])' on the first line?
- It is social [[triggered]] when people around the world react to it.

- Unfortunately, it appears that the brackets do not translate correctly.
    - Actual Design - [[Mechanical Design]] Concepts and Methods
    - `Actual design - [way of thinking and method of mechanical design]`
- Tags with sharps would be blanked out.
    - `[Three levels of design] : [Instincts, Behavior, and Introspection] #Instincts #Behavior #Introspection`.
    - `[Three levels of design]: [instinct, action, introspective] # instinct # action # introspective`

- Why don't you translate it into HTML with wget or something and then translate it?
    - Not much difference.

---
This page is auto-translated from [/nishio/Scrapbox英語化計画](https://scrapbox.io/nishio/Scrapbox英語化計画) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Sentence Summarization for the Age of Natural Language"
---

[Sentence summarization for the age of big natural languages, #Python - Qiita](https://qiita.com/icoxfog417/items/d06651db10e27220c819)
> There are three perspectives from which to organize the task of summarizing.
- > 2. [[Intention to prepare summary]].
    - You mention something I only recently realized, six years ago.
            - [[Refine the concept of summary]]
    - > On the practical side, there is an argument that simple summarization without instructions (Generic summarization) is meaningless (Automatic summarizing: factors and directions). This is an opinion with which I am personally quite sympathetic (especially when I look at the summaries I have actually tried to create).
    - ChatGPT makes it easy to summarize, and I'm starting to feel it too.

- Extractive
    - [[TextRank]]
    - [[Latent Semantic Analysis]]
- 2.2 Abstractive
    - [[Encoder-Decoder]]


> [icoxfog417](https://twitter.com/icoxfog417/status/1723530373370667058) When I read this, I wonder if what you really want to do is simply search? I don't think so.
>  >_stakaya: Sompo Japan's RAG commentary article was very good...
>  [[About Improving Document Retrieval Accuracy in RAG (Overview)]].

> [_stakaya](https://twitter.com/_stakaya/status/1723540096086061534) I'm wondering if this is an image of putting a chat skin over the search as a UI.

> [icoxfog417](https://twitter.com/icoxfog417/status/1723615500398408055) If we assume a search + summary value structure, I still have the impression that the summary contribution is closer to 0~20%.
>  "A simple summary that gives no instructions is meaningless" has been a point of view since 1999, but I feel that there should be more discussion on user intent/intention-based summarization beyond precise responses if it is to be a RAG.

> [icoxfog417](https://twitter.com/icoxfog417/status/1723616780915298469) I reread an article I wrote about 6 years ago, and I felt that the perspectives needed to improve the response experience in the RAG era were pointed out in a fairly ancient study.
>  I don't think we can get the experience we want just by using LLM, for example, update summarization when X number of consecutive minutes in chronological order are found in a search.
>  ![image](https://pbs.twimg.com/card_img/1723613902779691008/zy04jSIo?format=jpg&name=medium#.png)

> [icoxfog417](https://twitter.com/icoxfog417/status/1723618106852196753) It is quite difficult to take into account not only the minutes but also the articles if they are published in different years, and there are situations where the scope of the summary needs to be limited for reasons of copyright protection and internal reference authority (Indicative summary). There are also situations where it is necessary to limit the scope of the summary (Indicative summary) for reasons of copyright protection and internal referencing rights.
>  I think there is still a long way to go for the RAG experience, where search and summary each provide full value.


---
This page is auto-translated from [/nishio/大自然言語時代のための、文章要約](https://scrapbox.io/nishio/大自然言語時代のための、文章要約) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
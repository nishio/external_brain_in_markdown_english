---
title: "Extending the Red Link with AI"
---

2023-08-30
![image](https://gyazo.com/4d69e9d9b57633554d06698e00c3ca29/thumb/1000)

- [[AI writes research notes daily]] Useful use cases for the system that were not originally intended.
- [[Extension of red link]]
        - [[red link]]

History
- Originally, the AI was designed to read the "latest AI notes page" and create one new unnamed page per day.
- In the process of experimentation, we wanted to try "other options" and made it possible to specify the page to read by URL (--url option).
- As a result, it is difficult to know what follows what when an unnamed page is created, so "[[overwrite mode]]" (--overwrite) has been added to append to the specified page
- After several times of writing "XXX" in the body when creating a new topic "🤖🔁XXX", I realized that it is not necessary for a human to do that, so I decided to use the title if the page is empty as an additional bug fix for another issue. I implemented it.
- Now if you create a [[red link]] (a link with an empty destination) and specify the red link, the page will be created using the results of a vector search on the link title
- This is useful
    - What kind of experience does it bring?
        - I think I've written something like this before."
        - (Sometimes assisted here by Scrapbox link suggestions)
            - If not, you had to use search and other methods to find them.
            - We can leave that to AI.
- Further Development
    - When there is a good "long phrase" in the AI's generation or in the past descriptions that the AI has uncovered, make it a link, like a marker.
    - Naturally, it will be a red link, which is so long that it is not expected to connect on its own, so we will "extend the red link".

Specific example 1
    - [[🌀Exchange Form D]], the AI "reaffirmed the importance of exchange in the problem-solving process."
- I didn't know what "the importance of exchange in the problem-solving process" was, so I red-linked it and stretched it.
- AI said, "Problem solving bridges the gap between the ideal and the current situation, and the exchange of information in the process is important." and I understood, "I see, you mean exchange of information is exchange."
- I wrote about this realization in [Information exchange is exchange
- After a while, "[Is the exchange style of knowledge exchange A?" The question arose
- The "[[Public as the object of the gift]]" that was created there was extended by making it a red link.

"[[search with description]]."
- Search with explanation of why it was shortlisted.
- [[Recommendation with explanation]]
- [[RECOMMENDATIONS WITH REASONS]]

---
This page is auto-translated from [/nishio/AIによる赤リンクの延伸](https://scrapbox.io/nishio/AIによる赤リンクの延伸) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
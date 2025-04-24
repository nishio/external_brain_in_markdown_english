---
title: "pVecSearch2024-03-22 look back"
---

Improvement of [/plurality-japanese/vector-search](https://scrapbox.io/plurality-japanese/vector-search).

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>A summary of the pVectorSearch project was created.

[[pVectorSearch]]
- This Scrapbox-centric project on [vector search
    - [[Vector Search in Nishio]], which includes development, experimentation, and discussion of

Development Progress
- April 29~May 31, 2023 ([[pVectorSearch2023-04-29~05-31]])
    - Initial thoughts on this Scrapbox [vector search
    - First, envisioned creating an API (as a tool for myself)
- June 2~5, 2023 ([[pVectorSearch2023-06-02]], [[pVectorSearch2023-06-05]])
    - Build [[qdrant]] on local Docker and experiment with various things.
    - Applying the knowledge of [Scrapbox ChatGPT Connector
    - Search and display hit texts and pages
    - Consider [parallelizing embedded API calls
- June 6, 2023 ([[pVectorSearch2023-06-06]])
    - Implement administrative functions (save search queries, generate permalinks)
    - Release, [[Vector Search in Nishio]] is released.
- June 7, 2023 ([[pVectorSearch2023-06-07]])
    - Crawl others' Scrapboxes ([/halsk](https://scrapbox.io/halsk), [/yuiseki](https://scrapbox.io/yuiseki), [/tkgshn](https://scrapbox.io/tkgshn))
    - Be able to search across multiple people's Scrapboxes
- June 13~15, 2023 ([[pVectorSearch2023-06-13]], [[Diary 2023-06-15]])
    - Consider [making non-public materials eligible for vector searches
        - Consider the unit of information for [Cross-sectional Vector Search
- June 27, 2023 Omoikane Embed([/omoikane/Omoikane Embed](https://scrapbox.io/omoikane/Omoikane Embed))
    - Introduced to the forum for [Democratic Inputs to AI
    - Overview: (in Japanese only)
        - System to automatically vectorize and index Scrapbox content
            - Additional data collected from Notion
        - Automatically run at 6am daily using Github Actions
        - Split into 500 tokens each and vectorize with OpenAI's Embedding API
        - Uploaded to Qdrant database for vector searching
    - Ver1: 6/29 [https://github.com/nishio/omoikane-embed/tree/v1.0](https://github.com/nishio/omoikane-embed/tree/v1.0)
        - Now run daily.
    - 7/23 [/omoikane/Working Memo:Omoikane Embed into other projects](https://scrapbox.io/omoikane/Working Memo:Omoikane Embed into other projects).
    - Ver2: 7/29 [https://github.com/nishio/omoikane-embed/tree/v2.0](https://github.com/nishio/omoikane-embed/tree/v2.0)
        - I started writing reports in Scrapbox.
        - Related: [[omni]].
    - 2023/8/9
        - Organized the code to make it easier to put into other projects.
        - [/omoikane/Omoikane Embed into other projects](https://scrapbox.io/omoikane/Omoikane Embed into other projects).
- 2023-09-22 omni writing report in Scrapbox moved to private project
- 2023-10-17 Plurality Vector Search released([/plurality-japanese/Plurality Vector Search](https://scrapbox.io/plurality-japanese/Plurality Vector Search))
    - Provides vector searches for the contents of [The Plurality Book
    - Data sources are manuscripts on Github and their machine translation
        - Additional RadicalxChange Blog articles were also collected.
    - [[implement /plurality-japanese/Vector Search]].
    - 10/18 [[make /plurality-japanese/RxC Blog a search target]].
        - Adding a target from Markdown
- 2024-03-21 [/plurality-japanese/vector-search-improvements](https://scrapbox.io/plurality-japanese/vector-search-improvements).
- 2024-04-02
    - [/plurality-japanese/⿻VecSearchJA](https://scrapbox.io/plurality-japanese/⿻VecSearchJA) Release
    - Work log: [[pVectorSearch2024-04-02]].

New Feature Proposal
- Pass the Scrapbox page name in the URL fragment with GET
- Allows "load it and prompt execution" from search results
- Ability to switch search targets
- Option to exclude hits on the same page

Challenges and Future
- Implementation of update function
- Stable operation of services (log management, error handling, etc.)
- Careful handling of search results containing non-public sources
    - How to achieve [[sharing of prerequisite knowledge]] for [careful deliberation

This is an overview of the pVectorSearch project to date. The project is underway to explore the possibility of using vector search technology to cross-search individual knowledge bases for collaboration and consensus building. The challenge of providing new options for intellectual production and discussion is likely to continue, with updates and improvements.


<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Keep it short and sweet.
<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>The following is a brief summary of VectorSearch's development progress.
- April 29~May 31, 2023: Initial thoughts on vector search and API concept
- June 2~5, 2023: Experiments in local environment, application of Scrapbox ChatGPT Connector findings
- June 6, 2023: Administration functionality implemented, "Nishio Vector Search" released.
- June 7, 2023: Crawl through other people's Scrapboxes and search across multiple people's Scrapboxes
- June 13-15, 2023: Study of making non-public materials searchable and cross-search of library holdings
- June 27, 2023: Omoikane Embed development, introduced to the Democratic Inputs to AI forum (omoikane)
- August 9, 2023: Organize code and make it easier to implement in other projects
- October 17, 2023: Release of the Plurality Vector Search against the contents of The Plurality Book.
Omoikane Embed is a system that automatically vectorizes content from Scrapbox and other sources and uploads it to the Qdrant database to provide vector searches. it is being upgraded in June and July 2023, respectively, to expand its capabilities.

---
This page is auto-translated from [/nishio/pVecSearch2024-03-22振り返り](https://scrapbox.io/nishio/pVecSearch2024-03-22振り返り) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "pVectorSearch2023-06-20"
---

from [[pVectorSearch]]
pVectorSearch2023-06-20
New Feature Proposal
Pass the Scrapbox page name in the URL fragment with GET
- On the Scrapbox side, create a UserScript that opens in a new tab.
- The receiver hits the API with client JS, loads it into a query, and performs a search.
- Now you can have a "Vector Search Related Pages" from any public project.
- It's annoying to have the whole content in the search history.

- I'd like to search only the diagrams from the page with my hand-drawn diagrams.
- I'm starting to think that excluding hits on the same page is a better default.

New UI proposal
![image](https://gyazo.com/6e99c7cd8a3697961f317e54a3ffb928/thumb/1000)
- + is all and - is none.
    - 2023/6/26 No, I don't understand what you mean if you don't explain, just write ALL and NONE.

2023/6/20
Searching from my phone while on a business trip resulted in an error.
- I couldn't deal with it on the spot, so I just checked.
- The problem is not reproducible.
- It's a free version of Vercel, so the log seems to be up to an hour, I don't know what the error was anymore.
It seems to be working fine for now, so I'll pass this time.
- I guess in terms of Next Action, I'd introduce Sentry.

New Feature Proposal
- Allows "load it and prompt execution" from search results
    - digest
    - roleplay (e.g. in computer RPG games)

2023-06-21
- client side
    - `Unexpected token 'A', "An error o"... is not valid JSON`
    - `Failed to load resource: the server responded with a status of 504 ()`
- server side:
    - `[POST] /api/search`
    - `Execution Duration / Limit 10.01s / 10s (timed out)`
- It's simply a timeout.
    - I guess the next action would be to improve the error message on timeouts or retry.

2023/6/26
- I could see a future where I included my own private sources and then inadvertently shared the search results that included them.
    - If it contains non-public sources, let's keep the share button out.

2023/6/27
- Create a mechanism to automatically update the system, assuming you have export privileges.
- Fork the current source and create a [/omoikane](https://scrapbox.io/omoikane)specialized version
- create anew
    - [[pVectorSearch2023-06-05]].
- The source code is scattered all over the place because of all the experimenting and piling up.
    - I'm sorry, but I'm terrible.
    - Sometimes they go missing if you don't organize them.
- Duplicate export code from etude-github-actions repository
- From the qdrant repository
    - I didn't pip freeze.
        - `$ pip install -r requirements.txt `
    - make_index_from_scrapbox.py
        - I was able to embed it.
        - [[Git LFS]] to save cache
    - from_pickle_to_qdrant.py
        - I could send it to qdrant.
        - I named the collection omoikane.
            - I was a little unsure whether or not to put it together with the other cross-search, but I thought it would be simpler to talk about it with fewer dependencies if I kept it separate.
- Around UI from nishio-vecsearch
    - Simplify by cutting down on unnecessary functions.
- deploy
    - Oh, shoot, I should have separated the part where data is plugged in from the server implementation.
    - Deployment runs in Github Action.
    - Vercel is confused by the TS for export to begin with.
        - oh no (used as an expression of despair or when giving up)
- Should we be honest and separate them?
    - omoikane-embed to insert vectors and omoikane-vecsearch to search
- I've got it.

2023-06-28
- Omoikane Embed, I'm getting a lot of duplicate hits from the same page after adding the ability to chop by 100 tokens.
- Easy to undo, but no fun.
- Or make sure to take only one case from the same page.
- But I forgot to commit the code for the chopping one, so it went back on its own.


---
This page is auto-translated from [/nishio/pVectorSearch2023-06-20](https://scrapbox.io/nishio/pVectorSearch2023-06-20) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
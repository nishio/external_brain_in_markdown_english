---
title: "Scrapbox Cross Search"
---

Officially implemented.

This page is a note before it was made
2019-03-25
I want to [[cross search]] Scrapbox
- I can't put it in a public place, but I have a glimpse of what I want to search for.
- It would be nice to be able to search for other people's projects when searching for my own.

2019-05-15 [https://twitter.com/shiology/status/1128228164121927680](https://twitter.com/shiology/status/1128228164121927680)
- I put in the Chrome extension.
- ![image](https://gyazo.com/2be9ed43b6059731a692a28f5396fd3b/thumb/1000)
- convenient


---
Proposal 1:.
- `https://scrapbox.io/<project_name>/search/page?q=test`
- in multiple iframes.
    - How about using the [[a little service]] mechanism?
- Result:.
    - Scrapbox adds `X-Frame-Options: SAMEORIGIN` to the response header so it can only be opened from within the same origin
    - → We can only achieve this with UserScript or Chrome extensions.

Proposal 2::
- Can this be achieved with UserScript?
- In the meantime, I was able to embed multiple project search result pages via JS.
- ![image](https://gyazo.com/67531165ff2f68bda039f28df59db46f/thumb/1000)
- Script: [[nishio#5c984440aff09e00003f0141]].
    - Only activated when the page name is [cross_search
    - Adding "? keyword" in the URL to search by that keyword.


---
This page is auto-translated from [/nishio/Scrapbox横断検索](https://scrapbox.io/nishio/Scrapbox横断検索) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
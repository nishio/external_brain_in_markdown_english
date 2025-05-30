---
title: "Place the book's table of contents in Scrapbox"
---

from  [[Wellhead 2022-01-20]]
Place the book's table of contents in Scrapbox
- What is the best way to put the table of contents of a book in Scrapbox?
    - For user convenience, it is preferable to have everything expanded down to the subheadings, just like in a book, and to be able to click to jump to them.
    - But if you do that with [[Symmetrical links]] in Scrapbox, all pages are connected with the table of contents as a hub, which is not good from Scrapbox's point of view.
    - I had no choice but to try to make each hierarchy into a page, chapter, section, paragraph... but I don't think it's a good prospect and it doesn't seem to work at all.
        - [/nishio/Root of the book](https://scrapbox.io/nishio/Root of the book)
    - I guess I'll just use a bulleted expanded view like a normal book and use the external link notation for one-way links...

from  [[Wellhead 2022-01-23]]
Place the book's table of contents in Scrapbox
- The problem with doing bookish navigation is not "no one-way links" but "two-hop links."
    - what does that mean?
    - If you link from the table of contents to every page, it's going to be a giant link!"
        - That's what a table of contents is for."
    - "If you link to each page from the table of contents, you'll get reverse links from each page as well!"
        - If reverse links only occur to the table of contents page, there is no problem, but isn't it rather convenient?
    - The essence of the problem is "the creation of 2hop links from each page to all other pages via the table of contents page."
        - And if you don't show smaller links first or something, "the big links overshadow all the links."
        - No, if you only link to each page from the table of contents page,[[2 hop link]]は生まれないはずです<img src='https://scrapbox.io/api/pages/villagepump/takker/icon' alt='/villagepump/takker.icon' height="19.5"/>
            - ![image](https://i.kakeru.app/7df83435ec8f3f659c524dc114bb76c1.svg)
                - [Hierarchical links should not be 2 hop links.
        - 2 hop link is when the table of contents page link is posted from each page.
            - ![image](https://i.kakeru.app/cdd09c3746dbfd10d63a0d172f679898.svg)
        - Oh my! I didn't know!<img src='https://scrapbox.io/api/pages/villagepump/nishio/icon' alt='/villagepump/nishio.icon' height="19.5"/>
            - Scrapbox's concept of links is too difficult.
            - ![image](https://gyazo.com/125d983f24f4d3a08e7b21d15da83fe0/thumb/1000)
            - You're right.
            - Thank you for confirming.
                - I'm glad you're right.
    - So it's counterintuitive to make a table of contents page.<img src='https://scrapbox.io/api/pages/villagepump/takker/icon' alt='/villagepump/takker.icon' height="19.5"/>
        - I tried it and it looks good.
            - [/nishio/(0.1.2) Benefits of reading this book](https://scrapbox.io/nishio/(0.1.2) Benefits of reading this book)
            - No 2hop link is created via Table of Contents
        - I was actually thinking of adding [[breadcrumbs]] to the side of each page, but decided to hold off on that (maybe make them one-way links?).
                - [[Disable 2 hop link]]
                - Oh I see, it opens in a separate tab...
                - Well, as for views, I don't think the official implementation will meet my needs, so I'm going to tweak it with custom views.

---
This page is auto-translated from [/nishio/書籍の目次をScrapboxに置く](https://scrapbox.io/nishio/書籍の目次をScrapboxに置く) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
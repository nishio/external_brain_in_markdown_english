---
title: "Weak Scrapbox for collaborative editing"
---

Scrapbox is great for collaborative editing, but what if we dare to weaken it?
- Gain another strength by weakening something existing [[Strategy Canvas]].

page unit lock
- One person with WRITE-enabled per page
- The edit button will attempt to acquire a lock, and if it does, it will be a general split view in a markdown editor such as HackMD.
- Editing is auto-saved in seconds
- User explicitly releases locks
- Lock is released if no renewal is made for a certain period of time.

What can be gained by this
- The program can be written via API in the form of an attempt to acquire a lock, and if it doesn't apply, retry in an hour, and so on.
- After acquiring a lock, there is a guarantee that user writes will not be covered, so there is no problem with a "read the entire page, do various processes, and then write it back" type program.
- For example, if you are writing something in a notebook and get stuck, you can write "@keicho" and close it, and the keicho bot will come and leave a question.
- [[scbot]] closer to realization

---
This page is auto-translated from [/nishio/共同編集の弱いScrapbox](https://scrapbox.io/nishio/共同編集の弱いScrapbox) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "page memory"
---

> In our previous study, we pointed out that one of the problems with vector searches is that the same thing is repeatedly hit. To solve this, we thought it necessary to implement a system that remembers "what we have read in the past". But we also wondered, "Do we really need to read something once and never read it again?" was also a question. Later, [[overwrite mode]] and [[multi-head]] were implemented, and the idea was changed to just create a new page if the context was different. This changed the read management from project scope to page scope. We now have the "title of the page used" in JSON format to read the titles of all previous outputs.
    - [[Do you need 🤖MMR?]]

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Give this feature a good name.
<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>Page Memory: Adding the element of memory to this "page" centered feature gives it the nuance of "remembering" past information.

I see.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
![image](https://gyazo.com/ee4e571fa7c0ea7aad70ad241c79ed47/thumb/1000)
- 1: First, early implementations did not distinguish between pages and notes
- 2: Once the ability to trigger manually was added, a mode was added to continue using the same page because auto-generated titles by date and time would be confusing and full of pages.
    - This is what I call "overwrite mode."
    - This made one page a series of multiple notes.
    - So by reading the whole page, I can now have variables in the scope of the whole page.
        - I'm only using this for read management right now, but it's essentially a page-by-page namespace, so you can put, for example, an explicit purpose, or parameters for prompts, etc.

- [[Pinning effect on the topic]]

---
This page is auto-translated from [/nishio/ページメモリ](https://scrapbox.io/nishio/ページメモリ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
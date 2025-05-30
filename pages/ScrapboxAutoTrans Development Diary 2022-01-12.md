---
title: "ScrapboxAutoTrans Development Diary 2022-01-12"
---

[[pScrapboxAutoTrans]]

[https://www.facebook.com/564923216/posts/10160013259473217/?d=n](https://www.facebook.com/564923216/posts/10160013259473217/?d=n)
- A static site that is generated when edited in Notion.
- I use [[Vercel]].
- nishio: I was trying to create a static site when editing in Scrapbox, so I'll just refer to the Vercel section!
- Jun Harada: After making this, I wonder at what point people would use this, but why are you trying to do that?
- nishio:
    - I want to put a machine translation in between.
    - Japanese output to Scrapbox is personally low-cost
    - I could try to send out messages in English if I wanted to, but I'm too lazy to do it.
    - There is more benefit in releasing a mechanically 60-point workmanship rather than a zero that does not start moving due to high static friction.
    - For context, I've translated most of the book myself, but I thought it would be more valuable to put it in Scrapbox than to sell it as an e-book, and I thought it would be better to have a connection with the projects that I use on a daily basis, which are updated frequently, than to put it alone. The project is in Japanese, so I decided to translate it by machine.
    - And there's one more piece of additional information, Scrapbox is trying too hard with JS and can't directly machine translate web pages.

[/villagepump/built an ultra-lightweight Scrapbox client](https://scrapbox.io/villagepump/built an ultra-lightweight Scrapbox client).
- I use [[Vercel]].
- Start by forking and tinkering with this for now.

[/villagepump/2022/01/12](https://scrapbox.io/villagepump/2022/01/12)
- I created a Vercel account.
- Forked and deployed [Scrapbox Reader
- You still don't understand anything.
- I'm just looking at the URL and hitting the API, so it'll show up for projects other than my own as well.
    - I'll figure out later if that's a good idea or not.
    - When I put in machine translation in the future, if I hit the translation API that's triggered and charged for access, the crawlers will step on it and I'll go bankrupt, so I'll have to at least include a determination of whether it's my project or not.
        - What kind of trigger is used to translate, it doesn't seem to be access
- Re-language what you wanted to do
    - I want a link to be made between my two or more different projects.
    - Not explicitly created as an inter-project link, but by common keywords
- The current Scrapbox Reader, first of all, does not display links within the same project, so you have to start from the point of creating it.

---
Tentatively named "ScrapboxAutoTrans" because it is difficult to handle without a name, but it is unknown if the key concept is an automatic translation
    - [[private/public division]] Solving problems, etc.
    - I don't do [[Scrapbox private to public transfer]] because I want the edits to become public as soon as I edit a page that is intended to be public.
- Like connecting multiple projects.
    - The biggest benefit for me and for this project is the combination of two public private projects.
    - Why not simply merge them because they are in different languages.

Not my immediate goal, but I'd like to embed Kozaneba.

What we did.
- Fork Scrapbox Reader
- Create an account in Vercel and deploy
- Slight modification
    - Linked and 2-hop ahead related pages can now be displayed.
    - Aside from the appearance, the information is.

Think about multiple projects
- Why not just hit both APIs?
- If you have both, just display both with "both available" at the top.
- If only one is available, silently display the one that is available.

After that is done, switch in the "user's language of choice".
- If I had chosen English.
    - English version
    - Machine English translation of Japanese version
- If I had chosen Japanese.
    - Japanese (language) version
    - Machine Japanese translation of the title of the English version only

I don't plan to do it, but I thought of it and made a note of it.
- Prepare a project foo that anyone can edit.
- When project/page is accessed, the API of foo/page is also tapped and displayed side by side
- With a few adjustments to the appearance, it becomes a "comment box".

Next, hit the two projects and display them side by side
- Before we do that, do you want to fix the link display a bit more and pull it upstream?

---
This page is auto-translated from [/nishio/ScrapboxAutoTrans開発日記2022-01-12](https://scrapbox.io/nishio/ScrapboxAutoTrans開発日記2022-01-12) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "ScrapboxAutoTrans Development Diary 2022-01-17"
---

prev  [[ScrapboxAutoTrans Development Diary 2022-01-13]]

Incremental Static Regeneration
- ![image](https://gyazo.com/6dc186055d1a7478fdc2b3d4322fe330/thumb/1000)
    - [https://vercel.com/docs/concepts/next.js/incremental-static-regeneration](https://vercel.com/docs/concepts/next.js/incremental-static-regeneration)
- I'd like to see the trial and error of the development process reflected right away, but maybe even 60x60x24 once it's in stable operation.
- Either way, it's a different cycle of translation, I feel.
- Fixed a buggy 2-hop link.
- I was trying to put in Google Analytics and realized I couldn't write raw HTML.
- Is the linked JSON fetched beforehand?
    - ![image](https://gyazo.com/d06ac322e1ff1e63372dae3704d6568b/thumb/1000)
- Maybe I'll map it to mem.nhiro.org or something.
    - smell of memo, memory, memex, mememt mori, etc.
- I'm aiming for translations, but I think I need a list page first...
        - [[Scrapbox look-back function]]
    - I don't use it because I'm annoyed by the pages it creates, but I'm thinking it would be good if a fixed URL could be opened and this look-back list would appear.
        - `https://scrapbox.io/api/pages/nishio/search/titles?followingId=5a893319c2a2f300142bde60`
- Admin Menu
    - Recognize that the user is me and bring up a menu with this and that.
        - Switch from Safari to Porter from the Scrapbox page in [/porterapp/Safari](https://scrapbox.io/porterapp/Safari).
- translation
    - The translated word text must be obtained by using the translated English string of the title as a key
    - Record the date and time of the translation
        - No need to retranslate if it hasn't been changed since the previous translation.
    - I don't think the trigger for translation should be access.
        - First, it needs to be translated in bulk, and if the title is not finalized, it won't even be accessed.
        - After that, retranslate once a day, updated in the last 24 hours
        - What should we do if we want to translate something that was poured in at an old date and time, like the Hatena Diary?
            - When you "retranslate those updated in the last 24 hours" above, do you check to see if those linked from there have already been translated?

2022-01-18
[https://nextjs.org/docs/api-reference/next/link](https://nextjs.org/docs/api-reference/next/link)

---
This page is auto-translated from [/nishio/ScrapboxAutoTrans開発日記2022-01-17](https://scrapbox.io/nishio/ScrapboxAutoTrans開発日記2022-01-17) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
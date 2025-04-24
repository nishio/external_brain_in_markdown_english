---
title: "2024-11-17 external brain thinking"
---

from  [[Diary 2024-11-17]]

There's also a feeling that [[automatic English translation]] might have stopped.
![image](https://gyazo.com/3917ba7c677367b442dfd29ecda7f8af/thumb/1000)
So it's not that the translation has stopped, but that the import is mocking it up.

Based on "[[Yasukazu Nishio's Scrapbox -> Yasukazu Nishio's External Brain]]", there is a growing sense of "[[Maybe I should quit importing to Scrapbox]]".

## look back
.
Then I remembered [[mem.nhiro.org]].
- but it doesn't have the data, it just hits Scrapbox's API when accessing it and renders it.
- Good features:.
    - Custom Domain Delivery with Vercel
    - Free UI design
- Bad features:.
    - Data is acquired via Scrapbox's API without a DB, so processing using data that cannot be obtained from Scrapbox is not possible.
- Read.
        - [[What is mem?]]
        - > 2022-02-24 I've decided to call it [[mem]] because it's tedious to say every time "based on Scrapbox content, customized views, and delivered using Vercel on a custom domain".
    - [[2022-03-08]]
        - Issues/needs of crossing multiple projects
    - [[Next-mem]]
        - Needs to span multiple services
- [https://github.com/nishio/mem](https://github.com/nishio/mem)

I put [[etude-github-actions]] together exactly one year ago (I started using it around April).
- > 2023-11-17 I didn't know anything about Github Actions, so I made it as a practice, but the experiment [[automatic translation of Scrapbox with Github Actions]] went better than I expected, so it went straight to the production phase.
- Automatic English translation.
- Good features
    - You're straddling the language barrier.
- Bad Characteristics
    - Difficult to indicate in the UI that the view is a translation since it is a Scrapbox
- [https://github.com/nishio/etude-github-actions](https://github.com/nishio/etude-github-actions)

- Also related to [Vector Search in Nishio
- The data is automatically taken and EMBEDDED.
- Experimental search across multiple projects.
- It should be possible to do [[extract dense masses]] from the EMBEDDING data as we did the other day
- [https://github.com/nishio/vecsearch-service](https://github.com/nishio/vecsearch-service)
    - Is this PRIVATE?
- embedding side
    - [https://github.com/nishio/omni](https://github.com/nishio/omni)
    - I created omoikane-embed and then applied it to /nishio.
    - from [[omni]] 2023-08-31
    - >  I have installed the [[Omoikane Embed]] system, which automatically makes [[Omoikane Project]] into an embedded vector, in this Scrapbox project/nishio.
- Then [[nihia]] was born, right?
    - from [[pNihia]] 2024-05-05
        - > [[⿻Plurality Assistant]] was useful to make GPTs for this Scrapbox reading assistant.
        - > Server side is in private repos: `nishio/vecsearch-service`.
- So [[Late May 2024, a turbulent time.]] started and now w


## Perimeter Search
- Obsidian Vault at [/villagepump/Quartz](https://scrapbox.io/villagepump/Quartz).
    - static rendering
- [/villagepump/JSON Canvas](https://scrapbox.io/villagepump/JSON Canvas)
    - [[Obsidian Canvas]]
- [/villagepump/Bluemo Obsidian vs Scrapbox consideration 202301](https://scrapbox.io/villagepump/Bluemo Obsidian vs Scrapbox consideration 202301)
    - > Three points of contention are scalability, communication with others, and website publication.
        - Good organization, I was thinking to myself as I wrote this far, "You have multiple needs mixed up that need to be resolved.
        - My needs are not necessarily equal to this, so I have to think it through myself properly.


- Consideration
Forked [/villagepump/Bluemo Obsidian vs Scrapbox study 202301](https://scrapbox.io/villagepump/Bluemo Obsidian vs Scrapbox study 202301) and created [/villagepump/view addition study 202411](https://scrapbox.io/villagepump/view addition study 202411).
After some thought.<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>
- Obsidian or Scrapbox is a false choice
- Since "flexible in expansion" is vague, make it a little clearer what kind of expansion you want to do.
- I want to extend the View.
    - Backend can remain Scrapbox.
        - Scrapbox can continue to be used for the Japanese real-time part.
    - The conversion delay is not a problem because it is a replacement for what was originally translated into English and published at a rate of once a day.
        - I've been importing into Scrapbox.
            - But then, for those for whom English is not their native language in the first place, it would simply be "a site that for some reason cannot be machine translated"?
            - Frustration with not being able to add to the UI that it is a translation.
            - I'm feeling like I don't want to rely on the "rewrite services without a write API by importing" hack anymore, since imports are now mocking me up.
    - In other words [[I want a place to host things after they are automatically translated into English]].
        - I'm thinking that the same mechanism could be used to host the Japanese version, and that new features could be added along the way.
            - [[The higher the level of abstraction, the wider the range of application.]]
            - The problem that because there are so many things we want to do, we have to raise the level of abstraction to be able to do them all, and as a result, we get too far away from the specific requirements, which reduces the clues for decision making.
        - Should we limit ourselves to English hosts for once?
            - There is a lot to be learned from actually doing it.
- Unknown if the Obsidian path should be followed in replacing View
- We're talking about [[Quartz]] two years ago at this time.
    - > V4 was released on 2023-08-20 and the configuration has changed significantly
    - > Hugo to [[Preact]].
    - >  I wasn't used to writing Hugo templates, so being able to customize the front end with JSX would be helpful.
        - [Obsidian published in Quartz v4 [https://ikorihn.github.io/digitalgarden/blog/Quartz-v4%E3%81%A7Obsidian%E3%82%92%E5%85%AC%E9%96%8B%E3%81%97](https://ikorihn.github.io/digitalgarden/blog/Quartz-v4%E3%81%A7Obsidian%E3%82%92%E5%85%AC%E9%96%8B%E3%81%97) %E3%81%9F]
    - Whoa, you can customize it with JSX, React-like.


## next action
.
- Read back [https://github.com/nishio/etude-github-actions](https://github.com/nishio/etude-github-actions)
- Create a new one with external-brain or something.
    - Save JSON
- Create Japanese-English Obsidian format with [ScrapboxToObsidian
- Quartz v4 to Github Pages
    - (/nishio-en and mem.nhiro.org are operated in parallel without erasing once)

imagination
- /nishio-en will not be updated as it is, and when it works with GitHub Pages, I'll pin the "see here" page and be done with it.
- MEM is another story.
    - I'd like to see them join forces in the long run, but not at this point.
    - Interesting things to do with embedding data could be derived from omni.

---
This page is auto-translated from [/nishio/2024-11-17外部脳考える](https://scrapbox.io/nishio/2024-11-17外部脳考える) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
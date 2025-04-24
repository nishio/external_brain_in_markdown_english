---
title: "ScrapboxAutoTrans Development Diary 2022-01-20"
---

from  [[ScrapboxAutoTrans Development Diary 2022-01-19]]

from [/villagepump/2022/01/20](https://scrapbox.io/villagepump/2022/01/20)
- [/villagepump/operating Scrapbox in multiple languages](https://scrapbox.io/villagepump/operating Scrapbox in multiple languages).
    - I was racking my brains about how to [/villagepump/handle multiple projects transparently](https://scrapbox.io/villagepump/handle multiple projects transparently) my Japanese project and my English project, but then I started thinking that maybe I should make them one project in the first place.
        - The reason why I separated the projects is that my Japanese project's top page looks like a pile of garbage to those who can only read English.
        - As a result, interrelated projects became fragmented and "we need a mechanism to discover the connections between projects".
        - Essentially, what was needed was a "narrower view of content for English speakers only".
            - [/villagepump/Scrapbox is poor at narrowing down](https://scrapbox.io/villagepump/Scrapbox is poor at narrowing down) so we couldn't make that happen.
                - I saw the discussion in the link and realized I had a "poor view of what you've narrowed it down to".
            - Maybe ScrapboxReader could do it?
                    - If you [[Attribute expressions in iconic notation]] and set the flag for English speakers
                - Write a specific icon notation on every page... that's a pain in the ass...
                - It wouldn't be that much trouble if you wrote it automatically.<img src='https://scrapbox.io/api/pages/villagepump/takker/icon' alt='/villagepump/takker.icon' height="19.5"/>
    - When doubts arise about the fundamental reason for the existence of something that is being developed, what should we do w
        - I'll just put on my Vibrams and take a walk. w
    - now that the policy is settled
            - [[It would be good to have a policy on how to proceed with the ScrapboxAutoTrans project going forward.]]
        - Machine translation is pending.
        - Merging two projects on Scrapbox
            - Flag the English version of a project as English using the iconic notation.
                - [[Merge of intellitech-en]]
        - Create a view in ScrapboxReader that shows only English-flagged items for English speakers.

---
This page is auto-translated from [/nishio/ScrapboxAutoTrans開発日記2022-01-20](https://scrapbox.io/nishio/ScrapboxAutoTrans開発日記2022-01-20) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
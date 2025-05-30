---
title: "ScrapboxAutoTrans Development Diary 2021-10-30"
---

plan
![image](https://gyazo.com/d9fc2917b653842e06c9a9e6701cd270/thumb/1000)

I've been thinking about making a Japanese Scrapbox into an English translated Scrapbox, or a dynamic Scrapbox into a static Scrapbox, or making part of a private project public, etc., but I'm not sure what to do.

New idea
- 1: Static HTML
    - I was worried about "what if I want to modify the English side after the conversion" with automatic translation from Japanese to English, etc. After the conversion, it shall be static HTML, and there shall be no human modification.
- 2: Insert automatic Japanese-English translation
    - At this time, "I translated the title and it clashed with the existing page" can happen.
    - So automatic generation of navigation pages is necessary.
    - You never know how you'll see the results of a machine translation and how you'll want to modify it until you try it.
    - By setting "do not edit after conversion," the system will "then copy and paste the English page into Scrapbox and modify it" and "adopt the manual translation instead of the machine translation at the next conversion.
    - Need a microformat to convey this instruction to the conversion engine
- 3: Merging from multiple projects
    - If we can "navigate in case of bumps when translating," we should be able to "navigate when merging from multiple projects."
    - You can also "publish a public tag page of a private project" here

to the discussion so far.
    - [[public to private transfer]]
- [[pScrapboxAutoTrans]]
- [[gatsby]]
- Use [/villagepump/scrapbox as database for static hosting](https://scrapbox.io/villagepump/scrapbox as database for static hosting).

---
This page is auto-translated from [/nishio/ScrapboxAutoTrans開発日記2021-10-30](https://scrapbox.io/nishio/ScrapboxAutoTrans開発日記2021-10-30) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
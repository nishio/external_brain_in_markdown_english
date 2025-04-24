---
title: "etude-github-actions"
---

[https://github.com/nishio/etude-github-actions](https://github.com/nishio/etude-github-actions)

I didn't know anything about Github Action, so I made it as a practice.
- An etude is a piece of music designed to help students master the skills of playing a musical instrument.
- However, the experiment [[automatic translation of Scrapbox with Github Actions]] went better than expected, so it went straight into the operational phase.
    - As a result of this, after some time has passed, you may find yourself asking, "Huh? Where's the translation function working?" and "Where is the translation function working?

- 4/20 [/villagepump/nishio/pUnnamed(temporary)](https://scrapbox.io/villagepump/nishio/pUnnamed(temporary)).
    - It was called "pUnnamed" at the time.
    - Later called [pScrapboxAutoTrans2023-04-18
        - This [[pScrapboxAutoTrans]] itself later became [[pContinuousTranslation]] and then [pEnglish
                - I thought that calling it "Translate" would cause narrow-mindedness due to discussions such as [[Blog text generation instead of translation]].

- 10/12 [/villagepump/workroom-2023-10-12](https://scrapbox.io/villagepump/workroom-2023-10-12)
    - > Where is the past code, where is it? ...I thought I couldn't find it, but it was in "Practice" w
    - Terrible W.
    - > Need a place to discuss good and bad translations
    - > Need to be available to non-engineering Japanese.
    - This is the story of [pPluralityBook

- 11/13~
        - [[Create a reader AI]]

Explanation of what we do
- Create Deno and Python environment
- JSON export from Scrapbox with Deno
- Translate with [DeepL API
    - [https://github.com/nishio/etude-github-actions/blob/main/translate.py](https://github.com/nishio/etude-github-actions/blob/main/translate.py)
- Diff with previous JSON
    - import sometimes fails (A), so I tried just the update diff instead of the whole JSON
    - [https://github.com/nishio/etude-github-actions/blob/main/diff_json.py](https://github.com/nishio/etude-github-actions/blob/main/diff_json.py)
    - The reason for this is that, especially in the early stages of development, there were changes in the translation without updating the original data due to changes in the system, so we did not filter by the date of update.
- Commit latest JSON and translated JSON
- Import translation difference JSON to Scrapbox
    - I tried to do a Python port because I couldn't figure out the cause of the problem, but eventually solved it by updating the diff.




Notation shaking [[github-action-etude×]].

[/blu3mo/Scrapbox Translator v3](https://scrapbox.io/blu3mo/Scrapbox Translator v3)


---
This page is auto-translated from [/nishio/etude-github-actions](https://scrapbox.io/nishio/etude-github-actions) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
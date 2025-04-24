---
title: "External brain GitHub work"
---

2024-09-08
- Repository made [https://github.com/nishio/nishio-hirokazu-external-brain](https://github.com/nishio/nishio-hirokazu-external-brain)
- Think about what to do next
    - I just have to think about it because I have a meeting in three minutes.
    - JSON Export, etc. is automated in the translation system.
    - Bring it in and create a backup system first.
    - Maybe this: [https://github.com/nishio/etude-github-actions](https://github.com/nishio/etude-github-actions)
        - ![image](https://gyazo.com/021a459efdd87f7d62cca42243fdfe81/thumb/1000)
        - The billing on DeepL was updated, but what's stopping you?
        - > This repository is over its data quota. Account responsible for LFS bandwidth should purchase more data packs to restore access.
        - Ah, the GitHub LFS.
    - 8/21 email.
        - > Git LFS has been disabled on your personal account nishio because you’ve exceeded your data plan by at least 150%. Please purchase additional data packs to cover your bandwidth and storage usage:
        - >    [https://github.com/account/billing/data/upgrade](https://github.com/account/billing/data/upgrade)
        - >  Current usage as of 20 Aug 2024 10:38PM UTC:
        - >    Bandwidth: 8.21 GB / 100 GB (8%)
        - >    Storage: 150.09 GB / 100 GB (150%)
        - ![image](https://gyazo.com/bff8d96967ddbe9f4ceb93d0c13e32f9/thumb/1000)
        - ![image](https://gyazo.com/733459f7f7c6c9090b12fb0aa8afa11c/thumb/1000)
        - 3 data packs and you're still overflowing.
        - I made it to four.
        - ![image](https://gyazo.com/90ed4b11eca06a9f53660a9117137cb4/thumb/1000)
        - ![image](https://gyazo.com/12bc68d243003c8244f7e33a778ea6b2/thumb/1000)
        - Hmmm, well, once and for all.
            - Do you have 150 GB of JSON?
    - etude-github-actions, as the name suggests, was created to practice GitHub Actions, and has been in production for a long time because it worked better than expected.
        - It's time to review
        - I think you're forgetting that we've considered this before.
        - [[etude-github-actions]]
        - [[pVectorSearch]]

Maybe, but I think you're cramming too many functions into one GitHub Actions.
- 1: Create a way to access the latest JSON without hitting the Export API from Cosense.
- 2a: from (1), translation, import to English Scrapbox
- 2b: From (1), insert to vector DB
Now (1+2a) and (1+2b) are running in parallel.
- It is easier to link with various other things if it is completed with only (1)
    - I'm sure there are other Cosense users who would like their Cosense data to be on GitHub in an easily accessible form.

I don't think you should put too much code in (1).

Regarding Translation
- I'm translating line by line at DeepL right now.
- As of 2024-09-08, when the GPT context length became longer, I think it's fine to pass it as a JSON list and have it return as a JSON list.


---
This page is auto-translated from [/nishio/外部脳GitHub作業](https://scrapbox.io/nishio/外部脳GitHub作業) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
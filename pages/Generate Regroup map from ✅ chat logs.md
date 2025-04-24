---
title: "Generate Regroup map from ✅ chat logs"
---

![image](https://gyazo.com/83fec466aa6464fd5cc5672f74dd1f2b/thumb/1000)


from [[pKeicho]]
I want the Regroup to open with one click from the 🤔chat log.
- How to do it.
- Generate Regroup map data on the server side and then open it.
        - [[✅Python to map Regroup]]
    - Screen Structure Plan
            - [[Sticky note layout of Regroup map generated from Keicho's logs]]
        - [[Try the Regroup conversion]]
        - [[✅ Make a sticky with selected keywords]]
        - [[✅ Briefly sticky note some of the questions.]]
- Make it work on a ✅ server
    - Just let the link suggestion API server do all the work.
        - Read and write from Firestore
        - Would you prefer keicho's server?
        - Rather bring link suggestions to keicho server?
        - The current Regroup export does not use link suggestion results.
        - Start small and do it on keicho server.
        - I had a server set up on Heroku specifically for this, not link suggestions.
    - Right now I'm working on a repository on Keicho's server.
        - The ID is hard coded, reads the local log, and outputs it with a fixed map ID.
            - That's more convenient for experimentation.
        - ✅Receive ID in request to this, read from Firestore and make a path to create a new one.


- Place a spinner on Keicho's side.
    - Copy URL dialog when complete
        - Because it is asynchronous, it is blocked when tabs are opened
    - No, the dialog is displayed when the menu is pressed, and the URL is displayed when the generation is finished, or
    - Can we do without the spinner?
    - ✅Trigger map generation from Keicho menu

- If we can do this, I'd be tempted to include just multi-line text instead of chat logs.
        - [[Generate Regroup map from 🤔multiline text]]

---
This page is auto-translated from [/nishio/✅チャットログからRegroupマップを生成](https://scrapbox.io/nishio/✅チャットログからRegroupマップを生成) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
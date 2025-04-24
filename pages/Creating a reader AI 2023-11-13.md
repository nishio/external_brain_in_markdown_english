---
title: "Creating a reader AI 2023-11-13"
---

from  [[Create a reader AI]]
Creating a reader AI 2023-11-13
from  [[Diary 2023-11-13]]
Create a reader AI

[[pEnglish]]
Publication of English Articles
- 1: First of all, /nishio is fine.
    - Small Start
    - There may be synergy with the automatic translation to /nishio-en by DeepL now
    - Small step up from "just machine translation of DeepL"
    - 1-1: GPT3.5 makes you "write" instead of "translate
        - Eventually we will probably stop translating the current DeepL translation and replace it
            - I wonder if it will be placed directly in /nishio-en.
            - Optimal placement is a consideration.
        - Are we really going to do it all?" "Wouldn't it be better to improve it through trial and error?"
            - Yes, we should not do everything from the beginning.
            - Small experiments should be repeated and improved.
            - I would suggest prompting them at first, but eventually fine-tuning them.
            - Readers don't assume they are native English speakers.
                - Target many people around the world who have learned English as a second language.
                - I want to output in a language that is easy to understand and machine translate.
        - This will be written by a machine and then reviewed and reworked by me.
            - So, in effect, it could be interpreted as "I wrote it with the assistance of a machine.
            - Then you can [[en]].
    - 1-2: Building a readership
            - [[It's easier to write if you don't expect others to respond.]]
        - Japanese is [[I am the reader]], so I can write without expecting others' reactions, and that's why it continues.
        - However, when the article is translated into English, the effect is that "if there is also a Japanese article, I will read the Japanese one" and readers will be lost.
        - As a result, we unconsciously seek "others' reactions to English articles".
            - This is not good.
        - You can create a being that is not a "stranger," that reads and responds back.
            - [[Reader AI]]
            - [logs](https://chat.openai.com/share/ecd22898-b6cb-4a16-ad96-c578e946e3b3)
                - I did this all together as a messy experiment, but I don't think we should split up the steps and not have them share memories.
                    - 1: Japanese to English (human translation, translation AI, or writing AI)
                    - 2: English to English (English reader AI, write observations in English)
                    - 3: English to Japanese (Translation AI)
                - If it were separated like this, it would not be possible to translate "so was so wa" in the third step
                    - I can look at it and realize, "I see, 'so-and-so' is an unknown concept.
                    - How do we resolve this?
                        - The 1 AI should be able to handle that neatly, making "sowasowa" the link and also the "sowasowa" correspondence.
                        - This is not just about this case, the various "links" on Scrapbox are conceptual handles and should be properly connected
- 2: Talk about putting it on Github
    - Vague.
    - Github Pages? wiki? self-hosted in Vercel? Use ([[mem.nhiro.org]])?
    - Certainly, some of the mechanical outputs do not feel appropriate to be placed in the Scrapbox
        - As long as it's saved in a form that can be checked later, it's a good thing.
    - Needs are not clear.
        - Do I read it, does someone else read it, or does an AI read it?

Next Action
- 1-2 1-2, 2, 3 to work on the command line.
- Move it with Github Actions and put it in a new private project


---
This page is auto-translated from [/nishio/読者AIを作る2023-11-13](https://scrapbox.io/nishio/読者AIを作る2023-11-13) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
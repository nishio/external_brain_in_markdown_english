---
title: "Nodal point of thought on Scrapbox and AI 2023/8/16"
---

There's so much going on that it confuses my mind, so I have a blank page to write on.

Some joint projects slow down
balance
Balance between humans and AI needs to be adjusted.
Humans have not yet discovered a form of communication with AI.
timidly

One Diary a Day
It's meant to be slow.
More important essential thinking is done by taking time to think (hypothesis)
The AI side can do it faster.
What we actually did
It's also beneficial
But,
Perspectives on the human side do not change.
Diverse perspectives


Whether pages should be separated or not

- [[multi-head]]
- There is more than one topic on which you want to develop your thoughts.
- Now the AI thinks what it wants to think, independent of humans.
- But I'd like to throw in the unorganized stuff that humans are thinking about right now.
    - I go to bed and wake up and the AI is one step ahead of me, which is good.
- I'm concerned that by having only one topic right now, throwing it at them will break the AI's current thinking.
- That concern should be eliminated.
- Like a branch in Git, thoughts develop in an observable path of development.
- We should have more than one branch.
- When you think about it like this, it is not obvious whether each commit should be a separate page or whether the branches should be combined into a single page
    - Scrapbox's top page dies to make each commit one page.
        - But that's not Scrapbox's fault for not being able to customize the home page.
        - When the old and the new clash, don't use the new as a reason to stop.
    - branch to one page.
        - You can have a long page.
        - but, well, is there any particular difference compared to the minutes or the study group presentation materials that you're putting in there?

Discovering Related Chunks
- I think we should include one vector search.
    - I doubt if it's good enough at the top.
    - Eventually trade-off between use and exploration
    - I took 3 top pages and ignored chunks from the same page.
- Connecting other people's projects hit by vector search

The idea is to give a keyword and take as initial candidates the pages that contain that keyword or have a link to that keyword.

Branch 1 page implementation
- Currently "Get the latest note" and "Create the next note after it with a new name".
    - Get Latest Notes" retrieves pages beginning with "🤖20" and sorts them by title.
- You can specify the target note.
    - But the current situation is that I've created a new note and it's going to be HEAD, so there will be one branch.
    - It would be nice if we could specify an export title that does not begin with "🤖20"
    - Let's add an overwrite option.
    - When overwrite ON, leaving the contents of the target page? Create a page?
    - No, Scrapbox itself has a history function, so can I overwrite it without worrying about it?
    - I'm not sure of the conditions for saving the history, should I leave it explicitly?
- `--url ... --overwrite` can now do it.

---
This page is auto-translated from [/nishio/ScrapboxとAIに関する思考の結節点2023/8/16](https://scrapbox.io/nishio/ScrapboxとAIに関する思考の結節点2023/8/16) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
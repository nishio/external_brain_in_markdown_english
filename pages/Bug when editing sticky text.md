---
title: "Bug when editing sticky text"
---

from [[pRegroup-done-2019]]
Bug when editing sticky text
- There is a serious bug on the PC version that when I try to write a sticky directly in the sticky edit mode, a blank screen appears. w
    - The reason you get a blank screen is probably because you're using the post-deployment one, not the development server, so you don't get the error message.
    - The phenomenon is probably that the edit of the sticky causes a change in items, goes to the server to save it, and when the change message comes back, it does not realize that it is your update and applies regenerate
        - I put the stickies in state because I want them to be undo edited, but I don't think they should be sent to the server until the edits are completed in the first place.
        - To begin with, it is strange that editing a new sticky directly edits items. Considering the performance when the number of items increases, etc., it should be a system that has "stickies being edited" on the side of the fast canvas for editing and does not drop to the canvas below until it is completed (same system as handwriting on a path).
        - Bug that editing sticky text updates its status in a path that does not raise the "Edit locally" flag.
- revision (e.g. of a rule, regulation, etc.)
    - The cause, as expected, is "applying regenerations without realizing it's your update."
    - But the above "should be done in the upper layers in the first place" is a major construction project.
            - What to do in [Faster drawing when updating sentences when creating stickies
    - Fixed here this time.
        - > Editing sticky text does not raise "Edit locally" flag
        - I never flagged it for local editing in the first place.
        - When editing locally, set lastUpdated to Date.now(), plus store it on the server
        - If the update notification from the server comes later than the local lastUpdated, ignore it.

---
This page is auto-translated from [/nishio/付箋テキストの編集時のバグ](https://scrapbox.io/nishio/付箋テキストの編集時のバグ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
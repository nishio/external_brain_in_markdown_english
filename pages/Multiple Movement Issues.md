---
title: "Multiple Movement Issues"
---

from [[pRegroup2020]]
Multiple Movement Issues
    - Lasso selection of 200 stickies and moving them around takes time for the screen to refresh
        - It's because the code for moving one sticky is being used all over the place, and it's causing 200 status updates to run.
    - Undo to go back one by one as you are moving individual stickies.
        - Undoable from the ground up to make the state Undoable, but it was not designed properly
        - Instead of "each state update should be subject to Undo", it should be "each user operation should be subject to Undo".
        - I thought "Undo is hard" with the image of old GUI implementation, but not so much.
            - If you follow the React Way of "no destructive updates to state," you can easily get back to a "state at a point in time" by simply keeping a reference to the state at that point in time.

---
This page is auto-translated from [/nishio/複数移動の問題](https://scrapbox.io/nishio/複数移動の問題) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
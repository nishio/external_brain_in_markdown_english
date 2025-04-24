---
title: "Faster moving of stickies"
---

from  [[Faster Drawing]]
Faster moving of stickies
    - Overlay at touch point
        - A mechanism that overlays the second Canvas as a layer for fast editing when editing, and reflects it in the first one after editing is complete.
        - Layers for fast editing can be placed on top at all times.
            - Check if the upper layer is transparent or not.
                - Well, if it's not transparent, just use the technique used in [[Imaging at zoom]] to make an image of it and put it on the background.
                - →It was transparent.
    - Asynchronous updating of the back layer?
        - This can be put off to a later date at worst.
        - Initiate window system
            - Overlays shading on the moving target and draws only the window being moved.
            - Don't erase old ones.
    - Verify that it is feasible at a realistic speed as it looks
- special timing
    - Moving stickies when there are 100 stickies out is also slow.
        - This would be a good idea to include the "border drag" that the Initiate window system used to employ.
        - If you move the sticky itself, it'll take 0.5 seconds to delete the sticky on the canvas behind it, so you'll see two stickies for a moment.

[[pRegroup2020]]

---
This page is auto-translated from [/nishio/付箋移動の高速化](https://scrapbox.io/nishio/付箋移動の高速化) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
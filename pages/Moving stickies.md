---
title: "Moving stickies"
---

[[pRegroup-done-2019]]
- Moving stickies
    - First the sticky must be selected by a touch of the canvas
        - Sticky note pertinence
        - I have project.hitTest(point), so I guess I can leave it to you.
        - default tool
            - Handwriting with stylus
            - Finger touch to move
            - Move with mouse
            - [[Distinguishing between direct touch and Pencil touch on the iPad]]
    - Must be able to change position next
        - Now the stickies are just drawn, so at the very least we need to have a list of locations.
        - Both PointText and Shape can pick up events.
        - I tried to put PointText in the Shape child, but it didn't seem to work.
        - So I made a Group and made two of them that child.

---
This page is auto-translated from [/nishio/付箋の移動](https://scrapbox.io/nishio/付箋の移動) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
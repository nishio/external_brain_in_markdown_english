---
title: "Zoom with two-finger gesture"
---

    - Refactor [[Save previous center when moving screens]] for future implementation.
    - [[Parallel movement with two-finger gesture]]
    - Implemented in conjunction with
- > Zoom is reset to 1x at the start of zooming because it does not remember the amount of zooming just before
    - The value is saved when zooming or translating is completed, rather than just before.
    - Now TwoFingerGestureManager has it.
    - In the future [[Make position and zoom URL parameters]].
        - It's a STATE LIFT UP.
[[pRegroup-done-2019]]

---
This page is auto-translated from [/nishio/二本指ジェスチャでズーム](https://scrapbox.io/nishio/二本指ジェスチャでズーム) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
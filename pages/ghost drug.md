---
title: "ghost drug"
---

![image](https://gyazo.com/e3e666c521d9bf58fe9a109e9871a128/thumb/1000)
- Show translucency (ghost) when moving stickies by dragging.
- Redrawing the entire canvas while dragging will result in a smudge depending on the amount of content.
- So, the sticky is duplicated at the timing of mouse down and drawn on the canvas of the sticky itself.

before and after

![image](https://gyazo.com/05a3a55f2b1680cd376bcad238586533/thumb/1000)![image](https://gyazo.com/25da5f0aa690f52c2f072a819dec1f39/thumb/1000)
In the before image, there is a rendering delay while dragging, so the image is choppy.
After is only occurring after the drop.
I've got 2,500 sticky notes out to reproduce this lean state.
In realistic use cases, waiting times are much shorter.
After, they'll just shuffle off when you're not paying attention while you're moving your gaze or mouse pointer to the next sticky.

relevance
    - [[Rendering process blocks path draw]]
    - [[The lasso choice is not ghosting.]]

[[pRegroup-done-2020]]

---
This page is auto-translated from [/nishio/ゴーストドラッグ](https://scrapbox.io/nishio/ゴーストドラッグ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
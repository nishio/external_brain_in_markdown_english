---
title: "Should be drawn in update descending order"
---

It was designed that way from the beginning, but this time it was temporarily turned off during the [[Design changes to the way items are held]] process, so I captured what happens if you don't do it.

As a metaphor for the "movement of things," it is natural for things that have been moved and placed to come to the forefront.
This is achieved by drawing in descending order of modification time, where "the last updated is drawn last".
If we do not do that (i.e., the order in which things are generated), the drawing will look like this video.
The sticky note will always be at the very back.
![image](https://gyazo.com/48782a94a178b2a028a6a23e7c307bfb/thumb/1000)

[[pRegroup-done-2020]]

---
This page is auto-translated from [/nishio/更新降順に描画すべき](https://scrapbox.io/nishio/更新降順に描画すべき) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
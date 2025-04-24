---
title: "Faster drawing when updating sentences when creating stickies"
---

- Updating text on a sticky" while creating a sticky also needs to be done on the upper layer.

- I put the stickies in state because I want them to be undo edited, but I don't think they should be sent to the server until the edits are completed in the first place.
- To begin with, it is strange that editing a new sticky directly edits items. Considering the performance when the number of items increases, etc., it should be a system that has "stickies being edited" on the side of the fast canvas for editing and does not drop to the canvas below until it is completed (same system as handwriting on a path).

[[pRegroup2020]]

---
This page is auto-translated from [/nishio/付箋作成時の文章更新に伴う描画の高速化](https://scrapbox.io/nishio/付箋作成時の文章更新に伴う描画の高速化) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
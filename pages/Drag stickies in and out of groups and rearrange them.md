---
title: "Drag stickies in and out of groups and rearrange them"
---

from  [[Sticky note selection and compression UI design]]
Dragging stickies in a group
    - When a sticky in a group is grabbed and moved,
        - Stickies appear in the group after the move.
        - This is because a new sticky object is created when the sticky position is updated, and the group still has a reference to the old sticky object.
    - I thought "dragging the front sticky while grouped moves the entire sticky", but it doesn't.
        - I thought you should be able to move a nameplate sticky to a child in a group, and vice versa, and make a child in a group a nameplate sticky.
        - Parallel movement can be done using the un-stickied area.
    - Addition/deletion of stickies and replacement with nameplates

[[pRegroup2020]]

---
This page is auto-translated from [/nishio/グループの中の付箋をドラッグで出し入れ・配置変更](https://scrapbox.io/nishio/グループの中の付箋をドラッグで出し入れ・配置変更) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
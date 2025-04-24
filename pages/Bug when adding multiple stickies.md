---
title: "Bug when adding multiple stickies"
---

Resolved "multiple line pouring in add sticky mode" no longer
→ [[Multi-line import dialog]]

---
Bug when adding multiple stickies
- When multiple lines are poured in add sticky mode,
    - The first blank sticky hasn't been erased.
    - The last sticky I added is still designated as editable.
    - After editing, Undo will not undo the edits.
- Batch import of multiple lines of stickies does not seem to be causing updates on the read-only side.
- This feature is only exposed in development mode, so the fix is a low priority.

[[pRegroup-done-2020]]

---
This page is auto-translated from [/nishio/複数付箋追加時のバグ](https://scrapbox.io/nishio/複数付箋追加時のバグ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
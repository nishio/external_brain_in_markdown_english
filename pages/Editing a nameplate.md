---
title: "Editing a nameplate"
---

- Open the Edit UI of a nameplate when creating a group

The current "the last item is editable" does not allow you to edit the nameplate in the group.
I guess I need to have an "editorial target."
For example, if you move a group while editing, the child elements of the group, the nameplate objects, will also be updated.
You can't continue editing if you have references to old objects, and having old references in the first place is a source of bugs.

The edit window should close when you move, and the reference should be null when you close it.

[[pRegroup-done-2019]]

---
This page is auto-translated from [/nishio/表札の編集](https://scrapbox.io/nishio/表札の編集) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
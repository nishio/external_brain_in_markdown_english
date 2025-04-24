---
title: "FIXED: Menu does not close in Material-UI"
---

Because `<Menu>` was included in the `<IconButton>`, after the MenuItem is clicked to close the menu, the click event is propagated and the menu is opened again.

It could be stopPropagation, but I decided that it is not supposed to put `<Menu>` inside of `<IconButton>` in the first place, so I put them in `<>.... </>`.

[[Material-UI]]

---
This page is auto-translated from [/nishio/FIXED:Material-UIでメニューが閉じない](https://scrapbox.io/nishio/FIXED:Material-UIでメニューが閉じない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
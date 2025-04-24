---
title: "BUG: Adding a sticky while a selection is being made with lasso selection creates a garbage sticky that cannot be moved on the screen."
---

from [[pRegroup-done-2019]]
- BUG: Adding a sticky while a selection is being made with lasso selection creates a garbage sticky that cannot be moved on the screen.
    - Because the overlay canvas is the current project for drawing the lasso selection, and stickies are created on the overlay canvas.
- The problem with bugs caused by the wrong active project is that there is a global state called "active project" in the first place, and the overhead of switching the active project is not high, so functions that touch something other than the default project should temporarily switch it in the function, return it, and then exit. should switch to the "active project", switch back, and then exit.
- Instead, we should use decorator-like functions that do that, and stop tampering with the global state directly.
    - onOverlayCanvas
- →done

---
This page is auto-translated from [/nishio/BUG:投げ縄選択で選択が行われている状態で、付箋の追加をすると、画面上に移動できないゴミ付箋が作られる](https://scrapbox.io/nishio/BUG:投げ縄選択で選択が行われている状態で、付箋の追加をすると、画面上に移動できないゴミ付箋が作られる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
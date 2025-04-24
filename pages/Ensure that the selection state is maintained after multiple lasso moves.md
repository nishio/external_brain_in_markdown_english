---
title: "Ensure that the selection state is maintained after multiple lasso moves"
---

from  [[Lasso selection to move several together]]
Ensure that the selection state is maintained after multiple lasso moves
- [[Lasso selection to move several together]] I was able to implement it.
- By the way, after selecting more than one in the lasso selection and moving on,
    - The position of the selected object is updated and redrawn,
    - Currently, the highlight of the selection target is not in the UNDO/REDO target state, so it looks like it was deselected.
- If it looks like it's deselected but it's not, you should be able to move it by dragging lasso again.
    - If you do that, you will die. The reason is simple: the PaperItem that the selection is pointing to has been re-created by the above redraw.
- This area will be easily resolved once the PaperItem reuse fix is in place, but it's on hold for now.
    - If you select it and move it, the selection will be canceled, according to the specifications.
        - [[state management]]
[[pRegroup2020]]

---
This page is auto-translated from [/nishio/投げ縄複数移動後に選択状態が維持されるようにする](https://scrapbox.io/nishio/投げ縄複数移動後に選択状態が維持されるようにする) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
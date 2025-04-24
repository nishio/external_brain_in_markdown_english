---
title: "Lasso selection bug"
---

from [[pRegroup-done-2019]]
Lasso selection bug
    - Dotted lines disappear by clicking or starting a new drag, but the highlighted state of selected stickies does not disappear
    - No group selected?
- The latter is simply an omission of implementation.
- In the former case, the implementation of highlighting the selection grabbed the selection at the time of LassoTool initialization, so the code to remove the highlight is running against the initial selection (`= []`), so the highlight is not removed.

---
This page is auto-translated from [/nishio/投げ縄選択バグ](https://scrapbox.io/nishio/投げ縄選択バグ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
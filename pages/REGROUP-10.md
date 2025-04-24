---
title: "REGROUP-10"
---

`REGROUP-10 - TypeError: undefined is not an object (evaluating 'o[t[0]].parent')`
After selecting a lasso and moving it on the iPad, the lasso is moved to a different item than the one I wanted to select.
- Are the coordinates off in the first place due to the timing of the selection?
:

```
TypeError: undefined is not an object (evaluating 'o[t[0]].parent')
  at moveItems (moveItems.ts:49:21)
  at onDragEnd (Lasso.ts:171:7)
  at onDragEnd (mouseEventStateManager.ts:413:19)
  at apply (mouseEventStateManager.ts:111:5)
```


Reproduction method unknown

[[pRegroup]]

---
This page is auto-translated from [/nishio/REGROUP-10](https://scrapbox.io/nishio/REGROUP-10) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
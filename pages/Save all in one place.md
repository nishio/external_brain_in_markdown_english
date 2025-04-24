---
title: "Save all in one place"
---

- question (e.g. on a test)
    - When viewing what you have written on the iPad on a PC, if you select multiple paths and move them around, they will be moved and redrawn one at a time.
- cause
    - The useEffect triggered a change in state.items to saveToServer.
- cope
    - setTimeout if not flagged by useEffect, flag it
    - If it's flagged, do nothing and go through with it.
    - saveToServer at the timing when setTimeout fires.

ts

```typescript
let toSave = false;
useEffect(() => {
  if (toSave) {
    // do nothing
  } else {
    toSave = true;
    setTimeout(() => {
      toSave = false;
      saveToServer(isReadOnly, state, mapname)
    }, 100)
  }
}, [state.items]); 
```


[[pRegroup-done-2019]]
---
This page is auto-translated from [/nishio/まとめて保存](https://scrapbox.io/nishio/まとめて保存) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
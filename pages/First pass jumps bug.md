---
title: "First pass jumps bug"
---

![image](https://gyazo.com/55537ca9d5975829b1dc159adde930fb/thumb/1000)
Bug where only the first path drawn jumps to the center of the canvas

In fact, stickies appearing in the center of the screen was also affected by this bug, but the addition of stickies did not feel strange because a human did not specify the position of the stickies
![image](https://gyazo.com/e4aca30fec3a4ffbc1d5fdba8295193c/thumb/1000)


cause
    - [[Zoom with full view when loading editor]]
    - After loading, the canvas display area is now calculated from the content "so that the entire content fits on the canvas" at the time of the first drawing.
- If you start with a blank sheet of paper, there is no "drawing after loading", so the drawing after the first path is the first drawing.
- The coordinate system is set so that the first drawing is in the center.
ts

```typescript
export const drawItems = () => {
  ...
  if (global.beforeFirstDraw) {
    if (!global.isViewportSpecified) {
      fitToContents();
    }
    setGlobal({ beforeFirstDraw: false });
  }
```

- BeforeFirstDraw: false for special pages that do not load data from the server, such as blank
    - `handleSpecialURLParam`

[[pRegroup-done]]

---
This page is auto-translated from [/nishio/最初のパスがジャンプするバグ](https://scrapbox.io/nishio/最初のパスがジャンプするバグ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
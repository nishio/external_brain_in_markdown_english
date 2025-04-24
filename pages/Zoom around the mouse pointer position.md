---
title: "Zoom around the mouse pointer position"
---

from [[pRegroup-done-2019]]
Zoom around the mouse pointer position
- Zooming is currently based on the center of the screen, but what is natural for humans is zooming centered on the mouse pointer position

Like this
ts

```typescript
export function zoomAroundMousePointer(
  initZoom: number, initCenter: paper.Point,
  zoomCenter: paper.Point, scale: number,
) {
  const v = initCenter.subtract(zoomCenter);
  let newZoom = initZoom * scale;
  let newCenter = initCenter.add(v.multiply((1 - scale) / scale));
  return [newZoom, newCenter];
}
```


It was bracketed to support not only Shift+drag, but also mouse wheel and two-finger up/down swipes on MacBooks.

---
This page is auto-translated from [/nishio/マウスポインタの位置を中心としたズーム](https://scrapbox.io/nishio/マウスポインタの位置を中心としたズーム) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
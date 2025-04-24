---
title: "Converts a scaling parallel shift of the origin center to the center of the screen center."
---

I want the result of dragging an image to be reflected in the translation of the canvas in Paper.js.
Image scaling is centered on the origin, while canvas scaling is centered on the center of the screen, so conversion is necessary.
Let v be the amount of movement of the image origin.
Even if the image origin has moved, there is no movement on the canvas if, for example, the zoom is relative to the center of the screen.
So, if the vector from the origin to the center of the screen is a, the magnification rate is s, and the zoom rate of the canvas after magnification is z

- $c ← c - ((s - 1)a + v) / z$

ts

```typescript
newCenter = currentCenter.subtract(
  rect.center.multiply(s - 1).add(V2(imageLeft, imageTop))
  .multiply(1.0 / newZoom));
```


The first is the "A" in the "A" column.

[[pRegroup-done-2019]]

---
This page is auto-translated from [/nishio/原点中心の拡大縮小平行移動を画面中央中心に変換する](https://scrapbox.io/nishio/原点中心の拡大縮小平行移動を画面中央中心に変換する) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
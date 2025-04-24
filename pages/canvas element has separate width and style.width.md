---
title: "canvas element has separate width and style.width"
---

> Note further that the height and width are the logical canvas dimensions used for drawing and are different from the style.height and style.width CSS attributes.
:

```
// Make a canvas that has a blurry pixelated zoom-in
// with each canvas pixel drawn showing as roughly 2x2 on screen
canvas.width  = 400;
canvas.height = 300; 
canvas.style.width  = '800px';
canvas.style.height = '600px';
```

[html - Canvas width and height in HTML5 - Stack Overflow](https://stackoverflow.com/questions/4938346/canvas-width-and-height-in-html5)

---
This page is auto-translated from [/nishio/canvasエレメントはwidthとstyle.widthを別個に持つ](https://scrapbox.io/nishio/canvasエレメントはwidthとstyle.widthを別個に持つ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
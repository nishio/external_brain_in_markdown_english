---
title: "Macbook trackpad for scaling and parallel movement"
---

I want to use two-finger gestures on the trackpad to move an object in the browser up/down, left/right, and zoom in/out.

Conclusion.
- These operations are communicated to the browser in the wheel event.
- deltaX, deltaY contain the amount of vertical and horizontal movement
- ctrlKey: true for pinch
- The wheel event is PASSIVE by default, so to stop the browser's default clone operation, you must first turn PASSIVE off.
    - `window.addEventListener("wheel", onWheel, { passive: false });`
    - see [EventTarget.addEventListener() - Web APIs | MDN](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)




---memo
from [[pMovidea]]
Parallel movement on Macbook touch screen
- [Detecting multi-touch trackpad gestures in JavaScript](https://kenneth.io/post/detecting-multi-touch-trackpad-gestures-in-javascript)
- Wheel events have X and Y.
    - (Z is also available)
- ctrlKey: true for pinch
    - Seriously? (It was serious.)

---
This page is auto-translated from [/nishio/Macbookのトラックパッドで拡大縮小平行移動](https://scrapbox.io/nishio/Macbookのトラックパッドで拡大縮小平行移動) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
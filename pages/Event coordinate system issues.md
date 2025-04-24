---
title: "Event coordinate system issues"
---

from [[pRegroup2020]]
Event coordinate system issues
The event.point argument of the Paper.js event handler is,
The coordinate system is not the browser's coordinate system (project coordinate system), but the coordinate system after transformations such as zoom of the canvas (view coordinate system).
So if you rewrite the center or zoom of the canvas while dragging, the movement difference will be wrong, and it may start vibrating in the worst case.
Right now, there happens to be a canvas for fast drawing overlaid on top of the target canvas to be dragged around.
It's working fine, though, because it doesn't update the center, etc. on the upper canvas while dragging.
Overlapping of multiple canvases with different center/zoom should be improved as it is a cause of future bugs

---
This page is auto-translated from [/nishio/イベント座標系の問題](https://scrapbox.io/nishio/イベント座標系の問題) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
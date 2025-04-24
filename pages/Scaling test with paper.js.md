---
title: "Scaling test with paper.js"
---

from [[pRegroup-done-2019]]
Scaling test with paper.js
    - [[Implement adding stickies on Paper.js]]
    - [[Scaling of 100 sticky notes on iPad]]
You should first try scaling in paper.js and observe the behavior before

- Can we try it without [[Hosting]]?
    - I wonder if I can see the development server from my iPad with local wifi, I'll try that too.
    - →I can access it from my iPad with no problem if connected to the same Wifi.


Zooming with Paper.js
- `paper.setup(canvas);`
- after the end of "aru
- `paper.install(window.app.paper);`
- thereupon
- `window.app.paper.project.view.zoom = 1.3`
- You can change the zoom (for now) with
- There is a setZoom, so it would be a good idea to bind that to the appropriate place.

Multi-touch handling
- Transcribe this honestly: [Multi-touch interaction - Web APIs | MDN](https://developer.mozilla.org/en-US/docs/Web/API/Touch_events/Multi-touch_interaction)
- Issue → [[Issue with simultaneous one-finger drawing during two-finger gestures]].
-----


- [retyui/react-quick-pinch-zoom: A react component that providing multi-touch gestures for zooming and dragging on any DOM element.](https://github.com/retyui/react-quick-pinch-zoom)
- [React Pinch + Zoom + Pan](https://gist.github.com/iammerrick/c4bbac856222d65d3a11dad1c42bdcca)

- [[Debug output in Chrome on iOS]]

---
This page is auto-translated from [/nishio/paper.jsでの拡大縮小テスト](https://scrapbox.io/nishio/paper.jsでの拡大縮小テスト) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
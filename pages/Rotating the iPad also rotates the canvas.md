---
title: "Rotating the iPad also rotates the canvas"
---

[[pRegroup-done-2019]]
Rotating the iPad also rotates the canvas
If you rotate the screen, the canvas rotates with it.
However, the rotation origin is the upper left by default.
The size of the canvas does not change in terms of the DOM, so areas that cannot be written in the canvas appear.
Should the canvas element be resized to detect changes in view size due to rotation?

- [[resize with React+Paper.js]]


---
This page is auto-translated from [/nishio/iPadの回転でキャンバスも回転](https://scrapbox.io/nishio/iPadの回転でキャンバスも回転) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
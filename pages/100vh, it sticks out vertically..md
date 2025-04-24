---
title: "100vh, it sticks out vertically."
---

- I had set the canvas size to `100vh - var(--toolbar-height)`, but when viewed on an iPhone, it was too long vertically, causing the toolbar to be hidden by scrolling.
- 100vh seems to be the length including the height of the address bar
    - [The difference between 100% and 100vh - Nadezda Govorin🖥](https://hysryt.com/archives/1092)
- Address bar is hidden when scrolling
- If the app doesn't scroll, the bottom of the page gets cut off when it's set to 100vh.
- The solution is to add `height: 100%` to all of them. and adding `height: 100%` to all of them solves the problem.
- I also added `user-scalable=no`, but I'm not sure if this is required.

[[pRegroup-done-2019]]

---
This page is auto-translated from [/nishio/100vhだと縦にはみ出す](https://scrapbox.io/nishio/100vhだと縦にはみ出す) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
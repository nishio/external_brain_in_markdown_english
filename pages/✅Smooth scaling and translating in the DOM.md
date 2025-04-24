---
title: "✅Smooth scaling and translating in the DOM"
---

I want to implement natively instead of implementing in JS that the coordinates of each element changes due to translation.
- In other words, put it all on top of one div, and then move that div in parallel.

Can you even zoom in and out?
- What is the relationship between zoom, scale and transform?
- zoom is non-standard, scale is a kind of transform

Actually, the base on which all stickies are placed does not need to be large (just display the overflow).
- Verification.
- I was able to ✅.
    - Scaling with scale

viewport
    - [[100vh, it sticks out vertically.]]
- I still thought I'd get scrollbars, but the hidden divs were being counted, so I set top: 0.

---
This page is auto-translated from [/nishio/✅DOMでのスムーズな拡大縮小平行移動](https://scrapbox.io/nishio/✅DOMでのスムーズな拡大縮小平行移動) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
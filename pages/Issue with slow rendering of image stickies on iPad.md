---
title: "Issue with slow rendering of image stickies on iPad"
---

from [[pRegroup2020]]
Issue with slow rendering of image stickies on iPad
The performance of the iPad is still slow at a stressful level.
Why does it sometimes redraw after the image loads and sometimes not?
→In Chrome on PC, once an image is rendered, it is cached and redrawn at high speed the next time, but this is not the case in Chrome on iPad.
- I tried to see if it would work if the number of images were small, but even if there is only one image, the behavior is that "the image is drawn with a delay of 0.5 to 1 second on the iPad," so to solve this problem, I need to implement the system in such a way that the already drawn objects are used as much as possible.
- The parts that are erased and redrawn for ease of implementation of Undo need to be reused on their own without being erased.

---
This page is auto-translated from [/nishio/iPad上での画像付箋の描画が遅れる問題](https://scrapbox.io/nishio/iPad上での画像付箋の描画が遅れる問題) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
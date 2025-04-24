---
title: "Why do image stickies move strangely?"
---

from [[pRegroup-done-2019]]
Why do image stickies move strangely?
- Performance issues?
- Is there a problem with the image sticky?
→On another map with no performance issues, only the image stickies move fast while other stickies can be dragged decently.
- I think it's because the image sticky has a quarter-sized Raster on the surface, and that's what's causing the problem.
→Conclusion: Chrome on PC has null width for images not yet loaded, whereas Chrome on iPad has 0.

---
This page is auto-translated from [/nishio/画像付箋が変な動きをする理由](https://scrapbox.io/nishio/画像付箋が変な動きをする理由) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
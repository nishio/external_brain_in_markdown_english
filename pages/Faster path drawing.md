---
title: "Faster path drawing"
---

In a heavy environment with 2500 sticky notes after
![image](https://gyazo.com/59a44c1fd2631ae0dbbc78075f4ed2f0/thumb/1000)
before
![image](https://gyazo.com/9d9a80f02b23641a74ef4d8fe6611241/thumb/1000)
- Faster paths
    - Resolving [Rendering process blocks path draw
    - Paths are written on the overlay.
    - Put into pathBuffer
    - The number written is displayed.
    - When I tap on the display, it drops down and a heavy redraw runs for the first time.

concern
- The pathBuffer should be flushed when switching tools, how should such code be written?
    - → refactored and created code that is called whenever the tool is switched.
- Undo will not trigger unless you drop down the path, which is counter-intuitive.
- After dropping down the path, when I Undo, they are Undo'd one by one. Should they be done in batches?

[[pRegroup-done-2020]]

---
This page is auto-translated from [/nishio/パス描画の高速化](https://scrapbox.io/nishio/パス描画の高速化) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
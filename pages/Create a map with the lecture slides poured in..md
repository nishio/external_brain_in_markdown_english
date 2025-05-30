---
title: "Create a map with the lecture slides poured in."
---

from [[pRegroup2020]]
Create a map with the lecture slides poured in.
- PDF Import
        - [[graphics sticky note]]
    - Create a map with 100 lecture slides poured into it (with in-app data).
        - Added the ability to import multiple lines of text at once, rather than creating dedicated data in the app.
                - [[Import multi-line text as individual stickies]]
    - Whether it moves at a realistic speed
        - Redrawing every time you move on the PC appears to blink.
            - It should be displayed after rendering is done, so it's not right to blink.
                - It's asynchronous because the Raster is drawn onLoad.
            - This was resolved by setting the position outside of onLoad
            - When you load an image that doesn't fit the size of the sticky, it'll be written bigger and then smaller.
    - Experiment with iPad
    - Consider whether to screen for demonstration
        - Just make one for now, and if it doesn't look like it's suitable for a demo, just use a different URL.
    - Instead of creating a function to Upload PDFs, first use the list of images already on the server.

---
This page is auto-translated from [/nishio/講演スライドの流し込まれたマップを作る](https://scrapbox.io/nishio/講演スライドの流し込まれたマップを作る) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
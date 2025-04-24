---
title: "Scaling of 100 sticky notes on iPad"
---

- Enough free space is needed for grouping after displaying 100 stickies.
- If you can easily zoom in and out with a two-finger gesture on the iPad, it's less of a burden on humans.
- See if this is feasible.
[[pRegroup-done-2019]]

-----

You should [[Implement adding stickies on Paper.js]] first.
- Right now, I'm reusing 5 year old code to make stickies in SVG.
- But if I think about using Apple Pencil for handwritten input in the future, I wonder if it would be better to use canvas.
- SVG and canvas may behave differently when scaling

---
Scaling of 100 sticky notes on iPad
- What we want to achieve with Regroup is the height of [[listing]] in [two dimensional arrangement
- When I built something similar five years ago, it could only display a mere 70 pictures.
    - So we decided that it was "not yet time to go electronic.
    - After displaying 100 stickies, sufficient free space was needed for grouping.
    - At the time, the image was for use with Macbooks and other PCs.
- Now relaunched is the image used on the iPad.
    - The difference between zooming out to view the whole picture and viewing individual stickies in detail is the difference in zoom level
    - It should be easy to zoom in and out with the two-finger gesture.
    - If I could do that, the current iPad would be good enough for my purposes.

You should quickly verify that scaling is possible as I expect it to be.

What we could have done yesterday:.
- Create a new map
- Add image or text stickies from the script at hand to the map

next
- About 100 sheets from past lecture materials to be poured into the system.
- Scaling is implemented.
- Verified that the iPad can zoom in and out without problems.
- Sorting and Verifying
---
This page is auto-translated from [/nishio/100枚付箋のiPad上での拡大縮小](https://scrapbox.io/nishio/100枚付箋のiPad上での拡大縮小) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
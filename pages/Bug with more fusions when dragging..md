---
title: "Bug with more fusions when dragging."
---


![image](https://gyazo.com/92da5150008b47838fab73b1e0f4766c/thumb/1000)

Note that the cause is interesting.
- The Paper.js used for drawing is added to the currently active layer at the same time that a Shape or other instance is created.
- Until recently, items such as stickies were managed as React states, and if they changed, the canvas was erased and redrawn.
- Redrawing everything on the mouse move event while dragging a sticky is a bit choppy, so I'm overlapping two canvases and updating the translucent object only on the top canvas while dragging.
- When "redrawing a canvas," the lower canvas was active.

Under the circumstances.
- Bug that was doing both updating React state when adding stickies and creating Paper.js objects.
- Until now, "Update React State" was causing "Redraw Canvas", so there was no problem.
- The design was changed so that objects added at this time would survive.
- And that's what was painted on the canvas above.

thereby
- After being dragged but updated, the sticky at the new position is drawn on the layer below
- Old stickies are drawn on the upper layer and will not disappear.
- There is no actual sticky there, so if you try to drag an old sticky, it will move the whole parallel
A phenomenon called

[[pRegroup-done-2020]]

---
This page is auto-translated from [/nishio/ドラッグするとふせんが増えるバグ](https://scrapbox.io/nishio/ドラッグするとふせんが増えるバグ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "pKozaneba2025-08-14"
---

I've been trying to get Devin to think about making Kozaneba WebGPU compatible, but he said, "I don't recommend it at this time."
It would require a fairly extensive rewrite.

Well, I knew you would.
If we do it, we can either do it as a new project, utilizing only our know-how, or we can do it as a new project.

What about WebGL? Devin's answer to the question
- > WebGL is supported by 96.57% of browsers as of 2025 and is more compatible than WebGPU. While faster rendering performance and physics calculations can be expected, development costs are very high and the current React/DOM structure will need to be completely rewritten. In particular, re-implementation of text rendering, accessibility support, and Scrapbox/Gyazo integration will be difficult.
- > There are also some issues specific to WebGL, such as text rendering difficulties and debugging difficulties. Currently, there are no clear performance problems, as we have already optimized with `fast_drag_manager.ts` and others.
- >  Therefore, we do not recommend migrating to WebGL at this time. It should be considered when specific problems arise, such as slow operation with thousands of small bills. We recommend gradual introduction of Canvas 2D API, virtualization, and improvement through the use of WebWorker.

To begin with, the current bottleneck is that the data is stored in Firebase as a single JSON and hits the size limit at about 2000 sheets.
So you're not at the stage of trying to change the drawing method?

Even at present, 1000 items of text would be a peanut, so simply clearing the size limit and changing the rendering engine to display 10,000 items would have no user value, I guess.
I have a feeling that's true.

I'm thinking of making the leaf nodes of a broadband AI thing a sticky note instead of just a dot.

I'm discussing this with Devin, and he wants to avoid WebGL even when creating new w
Maybe I'll get a second opinion from GPT5...
> WebGL offers the best performance, but is complicated to implement. three.js or Pixi.js can be used to achieve this, but it takes longer development time. canvas (konva.js) is easier to implement and is expected to perform well even with 20,000 images. Which do you prefer?

In the end, Devin was told by GPT5 that he was lying when he said, "You can expect sufficient performance even with 20,000 sheets.

---
This will lead to [[pKozaneba2025-08-26~27]] after this

---
This page is auto-translated from [/nishio/pKozaneba2025-08-14](https://scrapbox.io/nishio/pKozaneba2025-08-14) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Rendering process blocks path draw"
---

- [[Faster path drawing]] solves the problem for the time being.

After the path is finished, it falls to the canvas below and the redraw of the canvas below runs.
- This blocks UI threads.
- Therefore, it is inconvenient to try to draw paths in succession.
- However, passes are used to stand up and write letters and so on.

> Stop drawing down the path every stroke and delay it until it's time to do something else, like switching tools.
If this is for a single person, I think it's the right answer.
However, as a [[Remote Shared Whiteboard]], the transmission delay increases and is subtle.

---
Discussion for 2019/6
[[OffscreanCanvas]]
- Chrome on iPad was version 74.
- OffscreanCanvas], which came in at 69, allows Canvas updates to be done outside of the UI thread.

Or stop drawing paths down every stroke,
Do we delay until it's time to do something else, such as switching tools?
But, you know, this is not an essential solution.
The fundamental problem is that updating Canvas with Paper.js is a huge, undividable process....
I was drawing in a naive loop.
js

```javascript
for (var i = 0, l = children.length; i < l; i++) {
    children[i].draw(ctx, param);
}
```

[https://github.com/paperjs/paper.js/blob/767ce043bac216eb8a16c817c1d97046d0e01307/src/item/Project.js#L880](https://github.com/paperjs/paper.js/blob/767ce043bac216eb8a16c817c1d97046d0e01307/src/item/Project.js#L880)
I wonder if I could chop this loop and the part after it into separate callbacks and [[requestAnimationFrame]]?

I've been looking into OffscreenCanvas, and if we give up non-Chrome support for the time being.
Just moving the canvas to Offscreen seems to solve the problem of the rendering blocking the operation.
→Chrome on iPad is Safari, so it cannot be used on the iPad, which is important.


[[pRegroup-done-2020]]


---
This page is auto-translated from [/nishio/レンダリング処理がパスドローをブロックする](https://scrapbox.io/nishio/レンダリング処理がパスドローをブロックする) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
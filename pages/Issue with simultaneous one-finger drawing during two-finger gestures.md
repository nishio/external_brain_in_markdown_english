---
title: "Issue with simultaneous one-finger drawing during two-finger gestures"
---

OLD TITLE: Mouse drawing occurs at the same time, causing strange lines

solution
- Even if I do preventDefault in the touchstart handler, onMouseDown on the Tool side of Paper.js is called.
- The reason for this is that Paper.js grabs touchStart and relays it to mouseDown for touch-enabled devices in the first place: [src [https://github.com/paperjs/paper.js/blob/cc135eaba](https://github.com/paperjs/paper.js/blob/cc135eaba) 80943f78075f84ca430dc3152bd154e/src/view/View.js#L1078]
- So, what needs to be fixed is the handler side that I passed to Tool for drawing.
    - onMouseDown created a path object, but delayed it.
    - Check raw event object with onMouseDrag
        - If it is a touchmove and touches.length > 1, do nothing and return
→ Fixed!

---
- Why is a mouse event being fired when I'm preventDefaulting at the start of multi-touch?
- [https://developer.mozilla.org/ja/docs/Web/API/Document_Object_Model/Examples#Example_5.3A_Event_Propagation](https://developer.mozilla.org/ja/docs/Web/API/Document_Object_Model/Examples#Example_5.3A_Event_Propagation)
- [https://qiita.com/hosomichi/items/49500fea5fdf43f59c58](https://qiita.com/hosomichi/items/49500fea5fdf43f59c58)
- I see, since the handler for the tap is attached to the window, the one on the canvas is called first by default.
- Is it right to capture and stopPropagation?

- stopPropagation does not change the behavior.
- When I put useCapture on, contrary to expectations, only the draw occurs and the two-finger gesture doesn't work.

[[pRegroup-done-2019]]

---
This page is auto-translated from [/nishio/二本指ジェスチャ時に一本指での描画が同時に発生する問題](https://scrapbox.io/nishio/二本指ジェスチャ時に一本指での描画が同時に発生する問題) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
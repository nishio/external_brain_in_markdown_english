---
title: "Distinguishing between direct touch and Pencil touch on the iPad"
---

When looking at each touch in the touches event, there are two types: touchType == "direct" and touchType == "stylus". This distinguishes between the two.
[https://stackoverflow.com/questions/34986373/javascript-touch-event-distinguishing-finger-vs-apple-pencil](https://stackoverflow.com/questions/34986373/javascript-touch-event-distinguishing-finger-vs-apple-pencil)

Note that when I am emulating an iPad on the Chrome Developer Tools, and I am generating touch events with the mouse, touchType is not attached. I hope to eventually be able to emulate touchType == "stylus".

In the future, this may be compiled in [Pointer Events](https://www.w3.org/TR/pointerevents/), but at this time, it seems that the browser implementation has not progressed. [[Pointer Events]]

[[iPad]]

---
This page is auto-translated from [/nishio/iPad上でのダイレクトタッチとPencilタッチの区別](https://scrapbox.io/nishio/iPad上でのダイレクトタッチとPencilタッチの区別) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
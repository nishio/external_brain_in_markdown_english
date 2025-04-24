---
title: "If you draw with a pen while zoomed out, it rattles."
---

If you draw with a pen while zoomed out, it rattles.
![image](https://gyazo.com/316eb015efbf8feba08e084c2297aba4/thumb/1000)
This is because the coordinates of the events that occur in the zoomed-out state are more sparse than in the zoomed-in state, and this is caused by the fact that the coefficients of the path smoothing process should have been changed to match the zoom state, but they were not.

Need to be able to see the current zoom state of the state from the pen drawing tool.
[[Redux-ize]] and then do it
I could already see it.

[[pRegroup-done-2019]]
---
This page is auto-translated from [/nishio/ズームアウトした状態でペンで描くとガタガタになる](https://scrapbox.io/nishio/ズームアウトした状態でペンで描くとガタガタになる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
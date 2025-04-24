---
title: "Vertical Alignment of Text"
---

I had a toolbar with a height of 60px with text in spans as appropriate, but when I added an image with a height of 50px margin: 5px, it started to stick out at the bottom.
![image](https://gyazo.com/dd51c789e95217900e1979e679bc28ce/thumb/1000)

This is because the vertical-align of span is "baseline-align", so characters protruding below the baseline, such as g, will protrude. vertical-align: 50%; will move the text up by 50% of the line-height.

![image](https://gyazo.com/92b132528db2db25eb44ec71cc92b08c/thumb/1000)
If you want to center them exactly, you can move the amount that is off by px in the opposite direction, but since they will all be icons in the near future anyway, I decided not to try this time.
[[CSS]]

---
This page is auto-translated from [/nishio/テキストの垂直中揃え](https://scrapbox.io/nishio/テキストの垂直中揃え) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
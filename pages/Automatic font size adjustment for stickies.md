---
title: "Automatic font size adjustment for stickies"
---

![image](https://gyazo.com/04429673a388276b95d828e95b60ec78/thumb/1000)

- [[Line Break and English Word Prohibitions]]


String metrics in canvas
:

```
var c = document.getElementById("myCanvas");
var ctx = c.getContext("2d");
ctx.font = "30px Arial";
var txt = "Hello World"
ctx.fillText("width:" + ctx.measureText(txt).width, 10, 50)
ctx.fillText(txt, 10, 100);
```

[HTML canvas measureText() Method](https://www.w3schools.com/tags/canvas_measuretext.asp)
I can only take the width.

I was able to insert <br/> in SVG, but it doesn't seem to be possible in canvas
- English multi-line display
    - [https://codepen.io/nishiohirokazu/pen/jjNyye](https://codepen.io/nishiohirokazu/pen/jjNyye)
    - We're chopping it up by the word and measuring metrics.

There is a possible breakable:0/1 attribute between the letters.
- For now, I'll just target Japanese and set everything to 1.

lineheight

If you write 333 with point 0,0 and size:100 and getBounds
- ctx.measureText("333")
    - TextMetrics {width: 166.845703125}
- window.x.textItem.getBounds()
    - Rectangle {_x: -98.54999542236328, _y: -50, _width: 197.09999084472656, _height: 120, _owner: PointText, …}
"33."
- textItem.getBounds()
    - Rectangle {_x: -98.54999542236328, _y: -50, _width: 131.39999389648438, _height: 120, _owner: PointText, …}
- ctx.measureText("33")
    - TextMetrics {width: 111.23046875}

paper.getBounds.height is simply fontsize * 1.2

[[pRegroup-done-2019]]

---
This page is auto-translated from [/nishio/付箋の自動フォントサイズ調整](https://scrapbox.io/nishio/付箋の自動フォントサイズ調整) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
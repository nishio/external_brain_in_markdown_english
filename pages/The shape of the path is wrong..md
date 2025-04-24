---
title: "The shape of the path is wrong."
---

[[pRegroup-done-2019]]
![image](https://gyazo.com/ae40c881f2d3ed80e58525af64b9cd95/thumb/1000)
[[strokeCap]] = "butt".
square.
![image](https://gyazo.com/387752ecebaad15b5fd5a378223b36c6/thumb/1000)
If you make it ROUND.
![image](https://gyazo.com/908a3951f214806d8053178a0b6eb967/thumb/1000)

![image](https://gyazo.com/5e9662fe013a9689aef70fd70386f428/thumb/1000)
Because of the strange direction of the ends.

Another Pattern
![image](https://gyazo.com/4ab1f1c0ba7ef28cab0952281811c053/thumb/1000)
Sharp angle paths cause
![image](https://gyazo.com/9a3ce5543dbdbdc394c6309ad0c63f39/thumb/1000)
This means that since [[lineJoin]] is miter and miterLimit is 10 by default, spines up to 10 times the width can occur.
[https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/lineJoin](https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/lineJoin)
This is what happens when you use ROUND instead of MITER.
![image](https://gyazo.com/3ddcb06c36e111052d9bc89e61719a65/thumb/1000)
![image](https://gyazo.com/02a380abdd8f0796ad0a551bdd32b499/thumb/1000)

after
![image](https://gyazo.com/035cf6e6504dcdf7c5a7ba66336093c4/thumb/1000)


---
This page is auto-translated from [/nishio/パスの形がおかしい](https://scrapbox.io/nishio/パスの形がおかしい) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
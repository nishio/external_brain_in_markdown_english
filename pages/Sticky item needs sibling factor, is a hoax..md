---
title: "Sticky item needs sibling factor, is a hoax."
---

![image](https://gyazo.com/2dafa7207edd4878b119547db6274acc/thumb/1000)
[CodePen](https://codepen.io/nishiohirokazu/pen/wvzXPgV)

The statement "sticky item needs sibling element" is NOT TRUE. It works without sibling elements, as shown on the right above.
A sticky container may fit into a sticky item when there is no sibling element. In that case, it does not move because there is no space to move.
So "sticky containers need to be spread out over the area where you want the sticky item to move" is correct.
In the above example, the flexbox effect is spreading without doing anything in particular, and for demonstration purposes, only the left side has been shrunk with height: fit-content.

[[position: sticky]]

---
This page is auto-translated from [/nishio/スティッキーアイテムに兄弟要素が必要、はデマ](https://scrapbox.io/nishio/スティッキーアイテムに兄弟要素が必要、はデマ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
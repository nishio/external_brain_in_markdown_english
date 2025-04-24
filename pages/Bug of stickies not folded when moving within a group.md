---
title: "Bug of stickies not folded when moving within a group"
---

![image](https://gyazo.com/7f72fa5bfb7940f9093ddbe6bcd239b1/thumb/1000)

2020-12-28 Fixed bugs

If a sticky in a group is moved within the group, the top-level drawOrder should not be updated. Because it is not a top-level element.

In the above example of bug behavior, when B is moved, the position of B in the drawOrder is moved, and since it does not exist, the behavior is "added to the end".
Therefore, there will be both a "group containing A and B" and a "sticky called B," and B will remain even after the group is closed.

At any rate, I fixed it so that drawOrder is not updated when that condition occurs.
However, currently, the stacking order does not change when stickies are moved within a group.
Since stickies in a group are drawn in the order of the group's childlen, should we update that?

---
This page is auto-translated from [/nishio/グループ内移動で畳まれない付箋発生バグ](https://scrapbox.io/nishio/グループ内移動で畳まれない付箋発生バグ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
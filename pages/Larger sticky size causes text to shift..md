---
title: "Larger sticky size causes text to shift."
---

fixed
![image](https://gyazo.com/4babe77e988a3d5dd0ee5385840b4586/thumb/1000)

diff

```
- let yOffset = calcYOffset(lines.length, fontsize);
+ let yOffset = calcYOffset(lines.length, fontsize / scale) * scale;
```

![image](https://gyazo.com/26866fc23074bfb275cc14807b959d71/thumb/1000)

[[pRegroup-done]]

---
This page is auto-translated from [/nishio/付箋サイズが大きくなると文字がズレる](https://scrapbox.io/nishio/付箋サイズが大きくなると文字がズレる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Explanation of the mechanism"
---

![image](https://gyazo.com/f95424776b71baab159b79b6fddbe54e/thumb/1000)

- Custom model items are placed in an invisible picture frame.
- As for the chairs, they are placed on top of invisible blocks (barriers) because there is a need to "sit on top of them".
- In the illustration image above, the bottom of the laptop is also invisible blocked, but this is usually done on a desk, etc.

Invisible picture frames can be obtained with the following commands
command

```
give @p item_frame{EntityTag:{Invisible:1b}}
```

If you are not used to installing an invisible picture frame, you can install a visible frame and then change it to invisible.
command

```
data modify entity @e[type=minecraft:item_frame, nbt={Invisible:0b}, limit=1, sort=nearest] Invisible set value 1b
```


[[Minecraft]]

---
This page is auto-translated from [/nishio/仕組みの解説](https://scrapbox.io/nishio/仕組みの解説) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Measuring circuit delays"
---

[https://youtu.be/ijQ5ppnMGlE](https://youtu.be/ijQ5ppnMGlE)

[[scoreboard]]
command

```
/scoreboard objectives add x dummy
/scoreboard objectives add dx dummy
/scoreboard objectives setdisplay sidebar x
```

command blocks

```
# X := 1
/scoreboard players set circuit x 1
# DX := 1
/scoreboard players set circuit dx 1
# X += DX
/scoreboard players operation circuit x += circuit dx

# DX := 0
/scoreboard players set circuit dx 0
```


---
This page is auto-translated from [/nishio/回路の遅延を計測する](https://scrapbox.io/nishio/回路の遅延を計測する) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
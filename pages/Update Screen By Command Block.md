---
title: "Update Screen By Command Block"
---

[https://youtu.be/mH1drg6q328](https://youtu.be/mH1drg6q328)

mycommand.yaml

```yaml
change_screen:
  command: /change_screen
  type: RUN_COMMAND
  runcmd:
    - "data modify entity @e[nbt={TileX:-680, TileY:68, TileZ:-39}, limit=1] Item.tag.CustomModelData set value $randomnumber%240<to>244%"
```


`/gamerule commandBlockOutput false`

[[Minecraft]]

---
This page is auto-translated from [/nishio/Update Screen By Command Block](https://scrapbox.io/nishio/Update Screen By Command Block) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
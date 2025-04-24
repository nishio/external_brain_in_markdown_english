---
title: "MyCommand memo"
---

:

```
giveitem:
  command: /giveitem
  type: RUN_COMMAND
  runcmd:
    - "/give @s wheat_seeds{CustomModelData: $arg1} 64"
change_screen:
  command: /change_screen
  type: RUN_COMMAND
  runcmd:
    - "data modify entity @e[nbt={TileX:-680, TileY:68, TileZ:-39}, limit=1] Item.tag.CustomModelData set value $randomnumber%240<to>244%"
test:
  command: /test
  type: RUN_COMMAND
  runcmd:
    - $Script$%Variable%foo+1
    - "/say foo"
    - $Script$%if%foo>5
    - $Script$%Variable%foo=0
summon_fish:
  command: /summon_fish
  type: RUN_COMMAND
  runcmd:
    - "/summon tropical_fish"
    - "/data modify entity @e[nbt={FromBucket: 0b}, sort=nearest, limit=1] FromBucket set value 1b"
```



---
This page is auto-translated from [/nishio/MyCommand memo](https://scrapbox.io/nishio/MyCommand memo) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
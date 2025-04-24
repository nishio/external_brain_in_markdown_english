---
title: "Armor Edition of Resource Pack in Minecraft JE1.17"
---

summary
- Armor model cannot be changed.
- Just edit the armor texture image.
    - Resolution can be increased by doubling the size of the image, for example.
- Using [[Blockbench]] is recommended
    - You can choose Armor or something else from the New Minecraft Skin and paint it while looking at the 3D shape.
    - ![image](https://gyazo.com/ba7daafdd8e632a6072b1fcef8f884a7/thumb/1000)
---
Armor model cannot be changed.
Just edit the armor texture image.
`assets/minecraft/textures/models/armor/iron_layer_1.png`
- ![image](https://gyazo.com/998aaf77c03ee5c76b1a6e2689568b5e/thumb/1000)

:assets/minecraft/models/item/iron_chestplate.json

```json
{
  "parent": "minecraft:item/generated",
  "textures": {
    "layer0": "cybozu:item/iron_chestplate"
  }
}
```


Try the finished product on a mannequin.
![image](https://gyazo.com/2463814b1b53125e4c9d6f94570dfac0/thumb/1000)


![image](https://gyazo.com/c0ee6689dcd495dce59d3310ae91e7c5/thumb/1000)

---
Blockbench
![image](https://gyazo.com/ba7daafdd8e632a6072b1fcef8f884a7/thumb/1000)
It's much easier because I can look at the 3D and work with it.
![image](https://gyazo.com/49b00262720f1a0afba7fbd8078fe2cc/thumb/1000)


---
This page is auto-translated from [/nishio/Minecraft JE1.17でリソースパックを作るArmor編](https://scrapbox.io/nishio/Minecraft JE1.17でリソースパックを作るArmor編) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
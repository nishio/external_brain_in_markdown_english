---
title: "Minecraft Fence Model"
---

assets/minecraft/blockstates/warped_fence.json

```json
{
  "multipart": [
    {
      "apply": {
        "model": "minecraft:block/warped_fence_post"
      }
    },
    {
      "when": {
        "north": "true"
      },
      "apply": {
        "model": "minecraft:block/warped_fence_side",
        "uvlock": true
      }
    },
    {
      "when": {
        "east": "true"
      },
      "apply": {
        "model": "minecraft:block/warped_fence_side",
        "y": 90,
        "uvlock": true
      }
    },
    {
      "when": {
        "south": "true"
      },
      "apply": {
        "model": "minecraft:block/warped_fence_side",
        "y": 180,
        "uvlock": true
      }
    },
    {
      "when": {
        "west": "true"
      },
      "apply": {
        "model": "minecraft:block/warped_fence_side",
        "y": 270,
        "uvlock": true
      }
    }
  ]
}
```


---
This page is auto-translated from [/nishio/Minecraft Fence Model](https://scrapbox.io/nishio/Minecraft Fence Model) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
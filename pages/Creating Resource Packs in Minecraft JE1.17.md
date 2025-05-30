---
title: "Creating Resource Packs in Minecraft JE1.17"
---

![image](https://gyazo.com/ce90a54c8ec00d03eb7769caf37d3428/thumb/1000)

summary
- Changing the texture of an existing model is easy.
    - I just need to change the image.
- Easy to change the design of armor and other items.
    - You can only change the texture of the model.
    - So the same difficulty as changing textures.
    - Using [[Blockbench]] is recommended
        - You can choose Armor or something else from the New Minecraft Skin and paint it while looking at the 3D shape.
        - ![image](https://gyazo.com/49b00262720f1a0afba7fbd8078fe2cc/thumb/1000)
        - Armor Edition: [[Armor Edition of Resource Pack in Minecraft JE1.17]].
- Difficult to change the shape of the block, complicated by various specifications
    - If you want something that is not a hit-and-miss item, you can make it as a hand-held item and put it in a frame.
    - All of the custom examples below are framed items (the framed models are reduced to 1/4 the size of the framed models).
        - ![image](https://gyazo.com/ea16067f3656b52bf69eeed8262343f4/thumb/1000)![image](https://gyazo.com/4d8ccf80f89415d429453c114f5e5de7/thumb/1000)![image](https://gyazo.com/9dd7207a3b0e3af21215aaee67518cd9/thumb/1000)

    - Block Edition: [[Block Edition to create resource packs in Minecraft JE1.17]].


---
Texture section below
- Armor Edition: [[Armor Edition of Resource Pack in Minecraft JE1.17]].
- Block Edition: [[Block Edition to create resource packs in Minecraft JE1.17]].

---
[Creating a Tutorial/Resource Pack - Minecraft Wiki](https://minecraft.fandom.com/ja/wiki/チュートリアル/リソースパックの作成)
I don't know, I read the

[https://www.youtube.com/watch?v=kp5iCZxEmt4](https://www.youtube.com/watch?v=kp5iCZxEmt4)
I figured it out when I saw this.
First, go to [.minecraft - Minecraft Wiki](https://minecraft.fandom.com/ja/wiki/.minecraft) to locate the Mycla file
- `Mac OS X	~/Library/Application Support/minecraft`
- Then zip and extract the jar in minecraft/versions
- There are various files in ASSETS.

Let's take a look inside.
assets/minecraft/blockstates/blue_terracotta.json

```json
{
  "variants": {
    "": {
      "model": "minecraft:block/blue_terracotta"
    }
  }
}
```


assets/minecraft/models/block/blue_terracotta.json

```json
{
  "parent": "minecraft:block/cube_all",
  "textures": {
    "all": "minecraft:block/blue_terracotta"
  }
}
```

That is, the shape is a cube with the same texture on all sides, and the texture is `block/blue_terracotta`.

By the way, I realized after I got here that `blue_terracotta` is the monochromatic one, and I was looking for `blue_glazed_terracotta`.
`assets/minecraft/textures/block/blue_glazed_terracotta.png`
- ![image](https://gyazo.com/7e633a24906f59778fdfc625fe5cfa55/thumb/1000)
- ![image](https://gyazo.com/331de1bb1118dddf092d2514d79e1bcb/thumb/1000)
- Let's replace this with another image

Once again, I remembered that what I am about to make is yellow, so look at `yellow_glazed_terracotta`.
assets/minecraft/blockstates/yellow_glazed_terracotta.json

```json
{
  "variants": {
    "facing=east": {
      "model": "minecraft:block/yellow_glazed_terracotta",
      "y": 270
    },
    "facing=north": {
      "model": "minecraft:block/yellow_glazed_terracotta",
      "y": 180
    },
    "facing=south": {
      "model": "minecraft:block/yellow_glazed_terracotta"
    },
    "facing=west": {
      "model": "minecraft:block/yellow_glazed_terracotta",
      "y": 90
    }
  }
}
```

This is a command to rotate the displayed model around the Y axis according to the block orientation information.

So, the model goes like this
assets/minecraft/models/block/yellow_glazed_terracotta.json

```json
{
  "parent": "minecraft:block/template_glazed_terracotta",
  "textures": {
    "pattern": "minecraft:block/yellow_glazed_terracotta"
  }
}
```


`assets/minecraft/textures/block/yellow_glazed_terracotta.png`
Bottom line, we should be able to replace this image.

Just put the files to be replaced under .minecraft/resourcepacks in the same directory structure as this asset.

Put in the resource pack you made.
![image](https://gyazo.com/3a6ab9a0a9dc4611cb60294460772654/thumb/1000)

![image](https://gyazo.com/80ff9a4badcdd1219a74150f382216ab/thumb/1000)
It's done.

revision
![image](https://gyazo.com/f159cb7954c614ab89a8aaeadca8a851/thumb/1000)
You can either replace X.png directly or put a new file and rewrite the reference from block/X.json
- Then the model of the item you have would be a rewritten one.
![image](https://gyazo.com/ce90a54c8ec00d03eb7769caf37d3428/thumb/1000)


assets/minecraft/models/item/yellow_glazed_terracotta.json

```json
{
  "parent": "minecraft:block/yellow_glazed_terracotta"
}
```

assets/minecraft/models/block/yellow_glazed_terracotta.json

```json
{
  "parent": "minecraft:block/template_glazed_terracotta",
  "textures": {
    "pattern": "minecraft:block/yellow_glazed_terracotta"
  }
}
```

assets/minecraft/blockstates/yellow_glazed_terracotta.json

```json
{
  "variants": {
    "facing=east": {
      "model": "minecraft:block/yellow_glazed_terracotta",
      "y": 270
    },
    "facing=north": {
      "model": "minecraft:block/yellow_glazed_terracotta",
      "y": 180
    },
    "facing=south": {
      "model": "minecraft:block/yellow_glazed_terracotta"
    },
    "facing=west": {
      "model": "minecraft:block/yellow_glazed_terracotta",
      "y": 90
    }
  }
}
```



Then put this on the server so that it will be applied without the participant having to configure the resource pack
    - [[Server Resource Pack Trial and Error Log]]

Right now I'm running the following shell script on my end (Mac)
resourcepacks/cybozu/build.sh

```
zip -r ../cybozu.zip .
shasum ../cybozu.zip
mv ../cybozu.zip ~/Dropbox
```

Write the displayed hash value in server.properties and restart the server.
The server configuration looks like this
server.properties

```
resource-pack=https\://www.dropbox.com/.../cybozu.zip?dl\=1
require-resource-pack=true
resource-pack-sha1=...
```


Client is asked to accept the server resource pack after logging in again
- I thought it would be downloaded if I accepted and proceeded, but it won't, why?
- It will be downloaded the next time you connect to it.

---
This page is auto-translated from [/nishio/Minecraft JE1.17でリソースパックを作る](https://scrapbox.io/nishio/Minecraft JE1.17でリソースパックを作る) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
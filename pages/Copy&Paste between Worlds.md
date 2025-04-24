---
title: "Copy&Paste between Worlds"
---

I was able to Copy&Paste between worlds.
![image](https://gyazo.com/9232a70499465d09800a27f8530e336b/thumb/1000)
copy source
- [Tokyo Skytree, tallest tower in Japan. HQ !! Minecraft Map](https://www.planetminecraft.com/project/tokyo-skytree-tallest-tower-in-japan-hq-/)
- ![image](https://gyazo.com/0d022853f06d0cad125817c0393f91e4/thumb/1000)
background
- ![image](https://gyazo.com/6cd6cb3cf14f85e46ca4d52043648371/thumb/1000)

Unfortunately, the antenna on the tip is broken.
Maybe the original was made using flat ground lower than Y=64 to Y=256, the upper limit of altitude, and this one was lost because it was placed at Y=64 on a normal map.
- >  The tower is almost 250 blocks-tall, that is close to the maximum height.
    - I knew it

This is annoying, it's hard to "make it one size smaller" with a microblock.

how to
    - I thought about using [[Structure Block at Microcosmos]], but 48x48x48 was the maximum size in JE
- Using [WorldEdit
    - > WorldEdit can work with “schematic” files to save or load your clipboard to disk.
    - >  To save your current clipboard to file, use `//schem save <filename>`.
    - >  To load a saved schematic, use `//schem load <filename>`.
    - [https://worldedit.enginehub.org/en/latest/usage/clipboard/](https://worldedit.enginehub.org/en/latest/usage/clipboard/)
- What we did.
    - Start server locally
        - I have WorldEdit in the plugin.
        - Replace world with the above distribution world
    - Select the area to be copied with `//wand` wand and `//copy -e`, `//schem save <name>`.
        - The file is generated like `minecraft_server/plugins/WorldEdit/schematics/<name>.scheme`.
    - Place this file in a similar path on the multiplayer server where you want to paste it
        - `//sheme load <name>`, `//paste` to.

important point
- You should look at the direction when copying with F3 to see which direction it will be pasted from your point of view and make a note of it.
    - Failing that, I pasted it and overwrote the existing one.
    - The block itself can be restored with `//undo`, but the teleporter that was destroyed at this time was created with the Slimefun4 function, and even if only the block was restored, it would not function as it was, so it needed to be rebuilt!

- [[Micra]]
---
This page is auto-translated from [/nishio/World間Copy&Paste](https://scrapbox.io/nishio/World間Copy&Paste) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
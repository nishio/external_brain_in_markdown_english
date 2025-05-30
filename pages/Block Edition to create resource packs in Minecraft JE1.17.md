---
title: "Block Edition to create resource packs in Minecraft JE1.17"
---

summary
- Difficult to change the shape of the block.
    - Complicated by various specifications
        - Surface culling of surrounding blocks, orientation, effect on lighting, etc.
    - If you want something that is not a hit-and-miss item, you can make it as a hand-held item and put it in a frame.
        - However, you can't stand on it or put things on it.
        - Example: The
            - ![image](https://gyazo.com/f6a27ae86f21dc4eb021e61dca6c03b0/thumb/1000)



---Trial and Error Log
![image](https://gyazo.com/fb204414fc85b8e822aca3dba10445f5/thumb/1000)

A rectangle can be placed in a 3x3x3 area one square up, down, left, and right from the location of the actual block.
- I thought, "I can make it to height 3," and then I thought, "What? I can't extend it?" But it can be made to be 3 in height by moving it one square down and one square up.
- A rectangle can rotate only in multiples of 22.5 degrees
- When replacing a model that is originally a cube, the display will be incorrect.
    - Giraffe(?) The ground under the feet of the giraffe(?) has disappeared.
    - This is probably an optimization that prevents drawing adjacent surfaces when blocks are adjacent to each other.

![image](https://gyazo.com/01d14822b4a4315f290cb4d31805e87a/thumb/1000)
- (I hit F2 repeatedly because the creeper came at the right time, but it showed the chat box.)
- I could make it look decent by floating the block in the air and not having it adjacent to other blocks.
- However, currently, the original position of the block has a hit detection and shadow display surface, so if you get on top of it, it will look strange.
    - There must be a way to control...
        - I heard on Discord that they don't have it.

> Optimization of not drawing adjacent surfaces when blocks are adjacent
assets/minecraft/models/block/cube.json

```json
{
   "parent": "block/block",
   "elements": [
       {   "from": [ 0, 0, 0 ],
           "to": [ 16, 16, 16 ],
           "faces": {
               "down":  { "texture": "#down", "cullface": "down" },
               "up":    { "texture": "#up", "cullface": "up" },
               "north": { "texture": "#north", "cullface": "north" },
               "south": { "texture": "#south", "cullface": "south" },
               "west":  { "texture": "#west", "cullface": "west" },
               "east":  { "texture": "#east", "cullface": "east" }
           }
       }
   ]
}
```


How to solve this problem heard on Discord
- Based on a model that does not trigger the cullface of other blocks.
- Put in the head slot of an invisible armor stand.
- Put in an invisible frame

Models that do not trigger the cullface of other blocks
- Glass, pressure-sensitive plates, flowers, etc.
- Flowers can't be placed on the wood block, so glass or pressure sensitive plates... what else is there?
- There doesn't seem to be any list of what doesn't trigger.
- electern also erases the bottom side
    - It seems to be hard coded as to which object erases the adjacent surface?

It's too delicate to replace the glass, so maybe a pressure sensitive plate...
- I'm starting to understand that it's a hassle to think about which objects to destroy and how they should behave, so let's add objects with mods.
- It's a hassle to have a limited number of slots.

Unlike blocks, items have model switching by parameters.
- Why isn't it on the block...
- So there is a way to make it as an item and use an invisible frame when placing it in the world.
    - This would make the slots inexhaustible.
    - But well, a frame can only exist attached to a block, so... hmmm.

Well, I'll take the pressure-sensitive version that looks the best.
- Woah, the pressure-sensitive version has no "placed orientation" attribute, so it can only be placed in a certain orientation.
- ![image](https://gyazo.com/044628ff5bc595c784fa338c266de4c3/thumb/1000)

Also, you've got a hell of a hold on it.
- ![image](https://gyazo.com/a99f24c058312fdf4a14f14f29be5458/thumb/1000)

[https://www.youtube.com/watch?v=aaJ8XgMAOno](https://www.youtube.com/watch?v=aaJ8XgMAOno)
I've decided to make itItem.

The way to hold it can be changed from "Display" in the upper right corner of [[Blockbench]].
- The truth is that holding it this way requires tremendous finger strength, but since I don't have the ability to hold my arms up and wait, I have no choice. If I hold it with both hands, I end up walking around kicking it with my knees.
- ![image](https://gyazo.com/fc1b39e9d7bf910b08a69551deb9ffb2/thumb/1000)

Adjust the appearance of the frame when it is framed.
![image](https://gyazo.com/e8b8b41b49bcfdd9524e23630647b5a5/thumb/1000)

Finally an acceptable look.
- ![image](https://gyazo.com/f6a27ae86f21dc4eb021e61dca6c03b0/thumb/1000)
- The small mouse pad-like thing in the back is a picture frame reduced to 1/2 size.
    - There was a suggestion to make it invisible, but I thought that having something invisible might be a trap, so I made it a size that would be hidden when you put things on it.
    - Items in the frame can be rotated by 45 degrees after being placed in the frame.
    - The MacBook itself was made into an item, not a block (stone axe).

Instead of directly rewriting existing models such as stone axes, etc., the macbook.json is inherited.
- When editing in Blockbench, it becomes "I want to edit MacBook, so I open macbook.json" and nature
    - It's not good to be like, "Well, MacBooks are stone axes..."
cybozu/assets/minecraft/models/item/stone_axe.json

```json
{
  "parent": "item/macbook"
}
```


- Q: Shouldn't the reference be `"minecraft:item/macbook"` or `"cybozu:item/macbook"`?
    - A: So far it's working fine.
        - When multiple resource packs are mixed, it is a good idea to separate namespaces to prevent unintended interference
        - In this case, we are not redistributing these resource packs, but rather combining them into one pack and making it a server resource pack, so it's just a hassle to separate namespaces internally.

Transparent table
- ![image](https://gyazo.com/18c3cc10a2fe794141708d0d59904e06/thumb/1000)
- First replaced cobblestone, but the top panel was not transparent
    - I replaced glass and it became transparent.
    - There appears to be a flag whether or not to consider the transparency of the texture.

How to introduce round chairs for sitting on Minecraft
- Only block to sit in GSit.
- Replacing the model of a block with a resource pack will cause culling of the faces of adjacent blocks and will not look right.
- Shifting the display position from the actual object is not allowed because it is not possible to change the position of the hit detection.
- solution (of equation)
    - Limit flooring materials
    - If you cull off the top surface of the flooring, you can put blocks on top.
    - First, make a material that looks like an office floor, and only where you pull it down, you can put a chair.
- another solution
    - Change the block's base model to turn off culling on the top surface
    - But this renders the top surface of all blocks in the ground.
- PS
    - Finally, we concluded to "replace the model when the half block is superseded" in combination with the lighting.

Flooring Limited Trial and Error:.
Replace the reference to cube_all, which is a concrete block that does not exist naturally and has a full culling in parent.
assets/minecraft/models/block/gray_concrete.json

```json
{
  "parent": "minecraft:block/cube_all",
  "textures": {
    "all": "minecraft:block/gray_concrete"
  }
}
```


Blocks without top culling
json

```json
{
  "parent": "block/block",
  "elements": [
    {
      "from": [0, 0, 0],
      "to": [16, 16, 16],
      "faces": {
        "down": { "texture": "#all", "cullface": "down" },
        "up": { "texture": "#all" },
        "north": { "texture": "#all", "cullface": "north" },
        "south": { "texture": "#all", "cullface": "south" },
        "west": { "texture": "#all", "cullface": "west" },
        "east": { "texture": "#all", "cullface": "east" }
      }
    }
  ],
  "textures": {
    "particle": "#all"
  }
}
```


The chairs on the right and left have holes in their feet, but the chair in the middle on the concrete is fine.
![image](https://gyazo.com/2dbb6fbc9512d31a81300cb62f0dbe35/thumb/1000)
But there's something wrong with the color...
- Oh, right, it's treated as adjacent to the block, so the lighting is zero!
- A superscript slab will not darken your feet.
- ![image](https://gyazo.com/7e48e11b5a4e971a7368b9a319a95c50/thumb/1000)


![image](https://gyazo.com/a9568e02e7146f87f7aa19236f210969/thumb/1000)
![image](https://gyazo.com/29ad883c9626a0252ab290d04fba3a30/thumb/1000)

I'm taking a development flow of updating the local resource pack files, reloading them with F3+T to test them, and then zipping them together into a server resource pack when finished.
- Server Resource Pack Update Process
    - Rewrite configuration file
    - Restart the server
    - When the client reconnects, it asks, "Do you accept the server resource pack?" they are asked "Do you accept the server resource pack?
    - Select Proceed, but no resource pack is loaded here (huh?).
    - The next time you connect, the resource pack is downloaded and applied (why?)

![image](https://gyazo.com/51059e841f25cd90ec23016ec290a156/thumb/1000)
mimicry
![image](https://gyazo.com/d9ec23684a555ac1a7ea64b7fbafc747/thumb/1000)
[Cafe, BAR and park! Cybozu's Nihonbashi office is an amazing combination of practicality and comfort.](https://cybozushiki.cybozu.co.jp/articles/m001002.html)
- Designed to be used in combination, so you can work with three luxurious screens.
- ![image](https://gyazo.com/4d8ccf80f89415d429453c114f5e5de7/thumb/1000)
- All keyboards are HHKB unmarked because of the hassle of creating textures.

[https://twitter.com/nishio/status/1447569969806405643?s=20](https://twitter.com/nishio/status/1447569969806405643?s=20)

[https://twitter.com/nishio/status/1447585160761798666?s=20](https://twitter.com/nishio/status/1447585160761798666?s=20)

[https://twitter.com/nishio/status/1448145564302860297](https://twitter.com/nishio/status/1448145564302860297)

---
This page is auto-translated from [/nishio/Minecraft JE1.17でリソースパックを作るBlock編](https://scrapbox.io/nishio/Minecraft JE1.17でリソースパックを作るBlock編) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
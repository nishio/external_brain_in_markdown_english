---
title: "Item copier in microcosm"
---

Started assigning custom models to items using NBT tags in Micra.
However, items made this way do not appear in the list of items, even in creative mode.
When adding this type of item to the world, I wondered if there was a way to do it in-game, since it would raise the bar for everyone except me to specify the item with NBT tags and execute the give and summon commands, and I thought that an item copier would be a good idea if there was one.
![image](https://gyazo.com/dc501843704a098a23f8b3626ec8a7f3/thumb/1000)
Put the item you want to copy in the left item frame and press the button in front of it, the command block will execute the command for copying and the same item will be in the left item frame

(computer) command
commands.yml

```yaml
  run_copy_machine:
  	- data modify entity @e[type=minecraft:item_frame,limit=1,nbt={TileX:-669,TileY:58,TileZ:-10}]
   	  Item set from entity @e[type=minecraft:item_frame,limit=1,nbt={TileX:-669,TileY:58,TileZ:-8}]
      Item
```


The original command is one line, but with line breaks and indentation for easier reading, it looks like this
:

```
data modify 
  entity @e[
    type=minecraft:item_frame, limit=1, nbt={TileX:-669, TileY:58, TileZ:-10}
  ] Item
set from
  entity @e[
    type=minecraft:item_frame, limit=1, nbt={TileX:-669, TileY:58, TileZ:-8}
  ] Item
```

Selecting an entity in an Item frame by specifying coordinates and assigning an Item in another Item frame to that Item.

By the way, if you remove things from the picture frame in creative mode, they don't go into inventory, so with this system, you have to go into survival mode once.
This is a hassle and I was wondering if I could use the summon command to spawn at the player's position, but I don't know how to give the result of data get as an argument to summon

Alternative solution, put it in a dropper and eject it at the player with a 1-tick delayed signal.

---
This page is auto-translated from [/nishio/マイクラでアイテムコピー機](https://scrapbox.io/nishio/マイクラでアイテムコピー機) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
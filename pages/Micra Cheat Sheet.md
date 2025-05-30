---
title: "Micra Cheat Sheet"
---

Purpose of this page: to provide compact pointers to useful knowledge for [[CybozuHackathon2021]] (knowledge highway) Compactness is the first priority, so please make a separate page for detailed discussion if necessary.

- The objective is to reproduce the office, so it is in creative mode. Objects are obtained inexhaustibly from the UI, which is opened with the `E` key. Right click to destroy, left click to install. The number of objects in your hand does not decrease when you place them. Space twice for flight state, space to ascend, shift to descend.
- `/` to enter a command, `/give <your_name> <item_name>` to get things without looking for them in a list, `/give <your_name> <item_name>` to get things that are not in a list and can only be obtained this way, `/give <your_name> <item_name>` to get things that are invisible and hit by a barrier, command_block to execute commands, bright airlight, etc.
- `//wand` to get the magic wand of the plugin [worldedit](https://dev.bukkit.org/projects/worldedit), by default a rectangular range selection, `//replace air dirt` to make the air in the selection dirt, `//set air` to make it all air = destroyed, `//copy -e` to copy including entities, `//paste` to calculate "the position of the selected area and yourself at the time of copying" from your current position and paste, `//undo`, `//rotate`, etc. as the names suggest. [[Copy&Paste between Worlds]] can
- You can get the in-game guide for the plugin [Slimefun4](https://github.com/Slimefun/Slimefun4) (hereafter SF) at `/sf guide`, you can get any SF item by changing the setting to cheat mode in creative mode ( Teleporter, etc.) There are tools that require research (Lumber Axe to take a whole tree with one click, etc.) Research can be done at `/research`.
- Can sit in `/sit` (plugin [GSit](https://www.spigotmc.org/resources/gsit-modern-sit-seat-and-chair-lay-and-crawl-plugin-1-13-x-1-17-x.62325/))
- `/hd create foobar Hello World` can produce strings in the air (see: [[https://filoghost.me/docs/holographic-displays/basics](https://filoghost.me/docs/holographic-displays/basics) Basic tutorial - Holographic Displays ]) Any item can be displayed "rotating up and down like an item on the ground" ([doc](https://filoghost.me/docs/holographic-displays/icons))
- `/image create <image_name|url>` to post images (plugin [Custom Images](https://www.spigotmc.org/resources/custom-images.53036/)), 1 block with 128 pixels Images can be managed in the kintone guest space app.
- Changing the design of your character, equipment, animals, etc. is "changing the skin" You cannot change the shape model You can do anything if you can edit the image, but I recommend [[Blockbench]] because you can only change the texture image.
- The customization of the shape and design of the objects placed in the world is done by switching models with the CustomModelData attribute of wheat_seeds (There are some models that were created before reaching this method, such as the Macbook assigned to a stone axe, but the unified method is less complicated to think about. I'm pulling everything towards wheat_seeds [[WheatSeedsSystem]])
- Enabling [[RCON]] so that any program can throw packets and execute commands.
- [[RaspberryJuice]] is included so that blocks can be installed from Python with the [[Minecraft Pi Socket API]].

---
This page is auto-translated from [/nishio/マイクラチートシート](https://scrapbox.io/nishio/マイクラチートシート) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
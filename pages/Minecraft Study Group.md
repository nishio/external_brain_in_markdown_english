---
title: "Minecraft Study Group"
---

Minecraft Becomes a Web of Voxels [PDF](https://github.com/kengonakajima/blog/blob/master/articles/minecraft_web.pdf).
- 2021-09-08 Slides by Kenmotsu Nakajima in "Technologies Supporting Online Games
- Nishio agrees with this interpretation, adding that
    - Minecraft in the first place.
        - In a 3D virtual space
        - We can collaborate.
        - platform
    - Cannot be ignored when considering the virtualization of physical offices
    - Good features: low cost for users to improve the place
        - Just as kintone has enabled "any employee can create and improve business applications
        - Virtual offices on Minecraft can be created and improved by any employee.

Minecraft's ecosystem as of 2021
- I'll explain this first.
- vanilla
    - An official original release (common noun).

- MOD (MOD server/MOD client)
    - Some were created early on and are still under development (e.g., [Forge](https://files.minecraftforge.net/net/minecraftforge/forge/)).
    - Modified server and client
        - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>How can you do that without documentation or source code?
    - Mojang hired mod authors and developed an API to facilitate mod creation
    - Need to match mod versions on client and server

- Two important elements arose after this
    - [SpigotMC](https://www.spigotmc.org/wiki/about-spigot/)
        - 2012
            - A community of mod authors & users advocating free/open source
            - More than 300,000 members
        - Knowledge sharing is now taking place.
    - Now available in vanilla client
        - ![image](https://gyazo.com/5841196691409c19e1603c045517e672/thumb/1000)

- Why is it now available to vanilla clients?
    - Resource Pack" feature added to vanilla
        - Additional model and texture changes can be made to create a new look and feel without modifying the client-side program
    - Accumulation of know-how to create additional function GUI with vanilla clients (see below)

- Available in vanilla clients, i.e.
    - Without using different software (MOD clients) for each server,
    - Serviced by a single software (vanilla client)
- This is the Web's
    - Without using different software for each server,
    - Services are available through a single software (Internet browser)
- So the same situation was created as
- Comparing to Web technology
    - Common Gateway Interface (CGI) is invented,
    - Run the program on the server side.
    - Dynamic behavior changes are now possible instead of static content delivery
    - This is what happened in Minecraft with the development of the plugin API
    - (To put a finer point on it, it runs in the same process as the server, rather than launching a separate process, so the situation is about the same as after mod_perl was born.)
    - Server-side implementation can be replaced as long as the API is followed.
        - Like turning Apache into Nginx.
        - This also occurs in Minecraft
            - Nowadays, PaperMC/Paper, which is touted as having improved performance over Spigot, is the mainstream.
            - [PaperMC/Paper: High performance Spigot fork that aims to fix gameplay and mechanics inconsistencies](https://github.com/PaperMC/Paper)

- So "Minecraft becomes a web of voxels."
    - Technically, it's already in that state.
    - Whether or not Minecraft becomes the de facto standard is the same as the browser market share battle.
        - Different layers of technology
    - What company owns Minecraft now?
        - September 17, 2014 [ASCII.jp: Minecraft acquisition is Microsoft's 'defensive move'](https://ascii.jp/elem/000/000/933/933106/)
        - > It also seems that Microsoft wanted the ecosystem that Minecraft would create.
        - >  Minecraft is not just a game, but can also be considered a cloud-based digital entertainment platform. The future potential of Minecraft may have been highly evaluated because of its aspects that go beyond the realm of a simple game, such as being not only a game itself, but also killer content for live-action videos and modification content through mods (modification data, an abbreviation for modification).

Minecraft Extensibility
- Create additional functionality GUI with vanilla client
    - ![image](https://gyazo.com/44401bcbf823b2d103ef59b4d54824e9/thumb/1000)
        - This is an in-game guide to a big-name industrialization plugin called Slimefun
        - It is actually a hack using the UI of a chest (a tool to store items)
            - The real chest is like this
                - ![image](https://gyazo.com/26d50a46a1f704e3ef3e96034b306ee7/thumb/1000)
        - Guide detail screen
            - ![image](https://gyazo.com/d4661d7820e35c8566e0219ca1911008/thumb/1000)
            - The UI of the chest and the hover text of the items explain what materials a nuclear power plant can be made from and what fuel it requires
    - Another example
        - ![image](https://gyazo.com/f899286d33e604335e721a48d0dde903/thumb/1000)
        - This is EconomyShopGUI, a plugin that introduces buying and selling of currency and items, which is also a chest
    - Plugin hooks into what is displayed in each slot and which slot is clicked
    - This is reminiscent of the "table layout" that used to be done on the web.
        - Hack to use the table tag for tabular layouts by removing all the rules and making it not look like a table, since HTML did not have the functionality to allow flexible layouts at that time.

- Plug-in development
    - Spigot carefully explains how to make one from scratch.
        - [https://www.spigotmc.org/wiki/spigot-plugin-development/](https://www.spigotmc.org/wiki/spigot-plugin-development/)
    - Nishio never built from scratch, but modifying existing plug-ins was easy.
        - Clone source code from Github
        - Install Maven
        - Fix source code
        - build
        - Put it in the server plugin folder and restart the server
    - Slimefun's Programmable Android has been
        - ![image](https://gyazo.com/13bbb1e3f3ead884f0b242b49ace8b6c/thumb/1000)
        - It was just a matter of repeating and executing a specified sequence of instructions.
            - ![image](https://gyazo.com/421282cca9dbe33e2b6735d6bdb2c1b7/thumb/1000)
        - Enabled Python to run w
            - ![image](https://gyazo.com/3c2874d8a7d6c3b3609124bdf9744f58/thumb/1000)

- protocol
    - Already analyzed.
    - The chest hack I mentioned earlier would
        - What kind of ID each slot in the chest has.
            - ![image](https://gyazo.com/b196dbe84fb8b2c7b6b9c9f2cdc17261/thumb/1000)
            - [https://wiki.vg/Inventory](https://wiki.vg/Inventory)
        - What packets fly when you click on a slot?
            - ![image](https://gyazo.com/522cdd83cae6491bf1264624f76543cc/thumb/1000)
            - [https://wiki.vg/Protocol](https://wiki.vg/Protocol)
        - is known

    - RCON
        - Protocol for executing administrative commands
        - Can throw packets from another process to execute in-game commands
        - [https://wiki.vg/RCON](https://wiki.vg/RCON)
        - Some commands are provided by vanilla, others are added by plug-ins
            - Examples of vanilla commands:.
                - Places a specific block on a rectangle at specified coordinates
                - `/fill <x> <y> <z> <x> <y> <z> <block>`
                - [https://minecraft.fandom.com/wiki/Commands/fill](https://minecraft.fandom.com/wiki/Commands/fill)
                - In the Java version, the destroy option performs itemization equivalent to mining with a pickaxe.
        - There is already a small program that throws RCON packets, so it is easy to control the server by throwing packets with cron.

- Bot Development
    - PrismarineJS/mineflayer
        - [GitHub - PrismarineJS/mineflayer: Create Minecraft bots with a powerful, stable, and high level JavaScript API.](https://github.com/PrismarineJS/mineflayer)
        - Can write client side in Node.js
    - Example of Nishio's work
        - Bots to harvest grown crops and plant new ones
        - [https://scrapbox.io/files/61517e27f11b61001db4a93b.mp4](https://scrapbox.io/files/61517e27f11b61001db4a93b.mp4)
js

```javascript
function find_grown_nether_wart() {
  return bot.findBlock({
    point: bot.entity.position,
    maxDistance: SEARCH_RADIUS,
    matching: (block) => {
      return (
        block &&
        block.type === mcData.blocksByName.nether_wart.id &&
        block.metadata === 3
      );
    },
  });
}
```

js

```javascript
const toHarvest = find_grown_nether_wart();
if (toHarvest) {
  const { x, y, z } = toHarvest.position;
  const goal = new GoalNearXZ(x, z, 1);
  if (!goal.isEnd(bot.entity.position)) {
    log(`move to harvest: ${[x, y, z]}`);
    await bot.pathfinder.goto(goal);
  }
  log("harvest");
  await bot.dig(toHarvest);
  log("done");
}
```


- Building Export
    - Server file format is also known so it can be read or generated programmatically
    - Even vanilla actually implements reading and writing to files.
        - Using "Structural Blocks"
        - ![image](https://gyazo.com/59dbb384903d640ec60abdf31a1992eb/thumb/1000)

- What Nishio hasn't tried yet
    - It should be possible to copy a part of a world and paste it into another world
        - Added: [[Copy&Paste between Worlds]].
    - It seems that the Java version and the Bedrock version (the version that runs on Switch, etc.) can be connected to the same server.
        - [https://github.com/GeyserMC/Geyser](https://github.com/GeyserMC/Geyser)
        - However, the Switch version does not have the ability to connect by specifying an IP address.
        - > On Minecraft Bedrock Edition, players on Xbox One, Nintendo Switch, and PS4 are limited to playing on 'Featured Servers' approved by Mojang/Microsoft.  [https://github.com/Pugmatt/BedrockConnect](https://github.com/Pugmatt/BedrockConnect)
        - BedrockConnect Solution
            - Server administrator sets up a DNS server
            - People who play on Switch will have to tweak their network settings to use that DNS server.
            - <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>That's... not a way I'd recommend to anyone for a minute...
        - Added: [[Connect to Minecraft Java server from Switch]].
            - I was able to connect, but it was slow.

Virtualization of physical offices
- A lot of people have moved to remote areas assuming they don't come to work in the after-corona.
    - Physical offices became less usable as a place for employee collaboration.
- Many people think about creating a virtual place.
    - Related services are myriad, but a few examples will be discussed
    - Oculus Room
        - Well-built model
        - Voice presentation utilizing device features
        - But customization is only a small option provided by the app
            - ![image](https://gyazo.com/c6c59b2bb9b4b76005d010212ea96163/thumb/1000)
            - [src](https://www.youtube.com/watch?v=dYas7tyMfuM)
    - VRChat
        - Both worlds and avatars are overwhelmingly customizable.
        - But if you try to create a world?
            - First, install Unity."
            - Many people drop out here.
        - Creating your own avatar is even more difficult than modeling, such as making sure the joints do not break down during animation.
            - Most people choose from what is available.
            - No sense of "being myself."
    - Minecraft
        - The world is composed of a combination of larger boxes.
            - Human-sized buildings are relatively easy to build by stacking blocks.
            - Anyone can make small tweaks, such as decorating with flowers.
        - Avatar is also a combination of square boxes
            - Paint is also coarse pixelated.
            - Easy to make by coloring in the browser.
            - Example: [https://minecraft.novaskin.me/#](https://minecraft.novaskin.me/#)
                - ![image](https://gyazo.com/d8c85588b8c8f8c76242ecc596cfb9e9/thumb/1000)
                - It looks like a complex shape that doesn't look like just a square box painted with color.
                    - In fact, there's one more layer to each body part, and it's used well for clothing and hair.
            - I made one too.
                - I don't have a particular idea of what I want to do, so I tried on clothes that I would normally wear. w
                - ![image](https://gyazo.com/d64736b2460b59fd7b4ee6359d497d09/thumb/1000)
                - This is basically without layers, only the pupils of the eyes are layered and placed in a non-pixel-like position.
- Not being able to customize it doesn't give it a "feel of our own".
- Outsourcing customization is expensive, and even if the financial cost is solved, it is a burden to translate requests into language.
- This is the same approach as the popular "employees create their own business systems using kintone" approach.
    - Business systems that cannot be customized cannot be fixed even if dissatisfied.
    - If you don't like it and outsource the system, it's expensive, and modifications are also expensive, so in the end you can't fix it even if you are dissatisfied with it.
- Shortfalls in the current Minecraft
    - No voice chat
        - We need voice chat with only those who have entered a certain distance or only those in the same room.
        - Technically, it should be possible to control the Discord audio channel from a plugin...
    - Let's have a party where all employees can get together on the micra!
        - This is a technical challenge, although it is easy to anticipate that the idea of
        - Limited to 20 simultaneous connections by default
        - It is easy to loosen the limit with options, but not easy to test how many people the server can withstand

Support for IT club activities
- If you already have a clear idea of what you want to do, then support it.
- People who do not have a clear idea of what they want to do.
    - While games are an incentive, we don't want them to just end up playing games.
- That's where Micra comes in.
    - It is better to build an automated device than to have a human being repeat a simple task.
        - In fact, in an unexplored junior server full of players who can think programmatically...
        - ![image](https://gyazo.com/02a3a4236531d4ba9debf26461609371/thumb/1000)
        - ![image](https://gyazo.com/48ba56f96cfd31f0349c13027800f1d1/thumb/1000)

    - It's better for a human to learn commands than to repeat simple tasks.
    - Add plug-ins to add useful tools, commands, and new game features
        - To do that, you basically need to read the English documentation on Spigot and Github.
    - Plug-ins are open source
        - If you don't understand something from the documentation, you need to read the source code.
        - Or put an issue on Github.
        - Or consult with us in English on our Discord channel.
    - If you're not happy with the plugin's functionality, you need to tweak the implementation.
    - and creates an incentive for a seamless modern programming experience from the game.
- In China, they fight with tank robots that eject gel bullets.
    - ![image](https://gyazo.com/0144b1af634190716b3caf22ef34dffa/thumb/1000)
    - Writing a program that compensates for manual control and creating an incentive to "learn programming to get stronger and win".
        - Learn to win" is the catchphrase.
            - ![image](https://gyazo.com/5170fa1ab74a3453ea083169c5c64836/thumb/1000)
        - To win, there will be an incentive to learn image recognition, etc.
    - But this approach would be difficult to adopt in Japan because of the strong allergic reaction to anything that reminds them of weapons.
    - Peaceful incentives are needed.
- cost
    - Server costs are a bottleneck for Minecraft multiplayer.
    - Roughly this kind of cost with Conoha VPS
        - ![image](https://gyazo.com/4f1d68559de5d04a260a1bca4027316f/thumb/1000)
        - I'm not sure this time, so I'm trying the middle one for now for 3 months.
            - 40,000 a year would be a heavy burden for elementary, middle, and high school students.
            - (I thought it would be convenient to have it installed as a template, but it was a vanilla server and I had to stop and re-install it on the first day of the program.)
    - If Cybozu were to provide this?
        - Looks good with lower SLAs than business system infrastructure.
    - How to avoid simply playing?
        - The same scheme as Cybozu's club support for employees could be used.
        - In other words, instead of providing funding, they ask for a report in a shared forum.
        - I want you to experience being on the side of disseminating technical information.
        - On the other hand, many teacher-parents have negative feelings about posting on the public Internet.
        - For example, how about using kintone as a closed social networking service?

- [[Online Collaboration]]

---
This page is auto-translated from [/nishio/Minecraft勉強会](https://scrapbox.io/nishio/Minecraft勉強会) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
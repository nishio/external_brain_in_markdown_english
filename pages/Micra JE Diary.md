---
title: "Micra JE Diary"
---

2021-09-19 I've learned a lot this past week, so I'll make a note of it.
![image](https://gyazo.com/acb5b341ffb730c790161d7825c67558/thumb/1000)

2021-09-10
- I jokingly added a micra emoji to a post about scheduling to play AmongUs on an unexplored junior gaming channel, and 9 people pushed it.
    - There's a demand for micro server.

2021-09-11
- I've only played Bedrock Edition (BE) on Realm (official online server), and I thought Java Edition (JE) would be interesting to add various mods to it.
- What do you want to do? I asked him, but he didn't have a very clear opinion.

2021-09-12
- At 5:00 a.m., the decision is made, "I can't see any particular policy even if I think about it, so I'll just do it the easy way first.
    - (It's the time of day, W.)
- Using [Conoha's Microphone Latin Plate](https://www.conoha.jp/vps/media/mine-semi/multi-server/)
    - I decided to do it and 17 minutes later I was already standing on the server, easy peasy.
    - I heard that Paper is good, but I'm not sure.
        - What I understood later:.
            - There are servers provided by the official and those that have been reverse engineered and patched.
                - I hadn't thought of that idea. I guess that happens when you have a long history and a lot of players.
            - PaperMC and Spigot are keywords.
- From there it took me 30 minutes to download the JE client and connect to the server.
    - I don't know how to make a torch.
        - Does JE have a "I don't know the recipe so it doesn't show up on the list" condition?
    - It started suddenly without going through the screen to specify seeding or game rules.
        - JE does not have such a screen, so if you want to change it, you need to change the configuration file or the administrator can use a command.
        - I was wondering why there was a command in BE since you can change it in the GUI in game, but I see, it's easier to change it with an in-game command than to rewrite the configuration file and restart the game.
- What, JE is not a harder monster than BE?
    - Spawned on a dark plain and was surrounded by zombies and died.
    - I was struggling to build a base of mud walls, and the nether gate was opened in 40 minutes and 2 days in the game, I feel the difference in civilization.
- After a round of multiplayer, we looked into Spigot and Paper and decided that we should stop the current server and start up a Paper server.
    - [Getting Started — PaperDocs 1.17.1 documentation](https://paper.readthedocs.io/en/latest/server/getting-started.html)
    - Default server, save data, etc. were in /opt/minecraft_server
    - I ran PAPER here.
    - Saved data in vanilla was converted automatically.
    - It accepts commands from the terminal, so it is common to run it in screen.
    - I'm not sure about systemd, so I'm holding off.
- Not familiar with user management
    - `$ adduser nishio`
    - `$ usermod -aG sudo nishio`
    - `.ssh/authorized_keys`
    - At least I can now log in with public key authentication.
- Plug-ins can now be included.
    - I want to render what's in the world.
        - I added [Overviewer](http://docs.overviewer.org/en/latest/), but it doesn't work well, probably because the save data format has changed.
        - [dynmap](https://www.spigotmc.org/resources/dynmap.274/) with
            - I wanted to see it in quarter view, but the default was a map from directly above, which confused me.
            - The quarter view had a confusing menu on the right edge of the screen.
                - ![image](https://gyazo.com/96fb6c4cfa1a48131b83d8fb6d1e43d9/thumb/1000)
            - It's interesting to see the architectural process that people are doing at a distance.
- Spawn chunks must be unprotected to allow other players to break the block.
    - `server.properties`: `spawn-protection=0`
- ssh is stuck without detaching from screen and cannot attach
    - `screen -dr`
- A new player came in and started building a farm.
    - ![image](https://gyazo.com/29be4f43b59ff3a9c6680e0fd1939eff/thumb/1000)
- I've added various plug-ins.
    - [holographic-displays](https://dev.bukkit.org/projects/holographic-displays) Instead of hard-to-see signs that can produce glowing holographic letters
    - [EconomyShopGUI](https://dev.bukkit.org/projects/economyshopgui): Shop functionality is in, but I thought it was user-to-user, but it doesn't look like it.
    - [worldedit](https://dev.bukkit.org/projects/worldedit), I haven't used it for edit purposes at all, but it's useful because it jumps over the block you're looking at with jumpto
- Server killed
    - 4GB memory VPS with `java -Xmx4G` is not right.
    - I set it to `java -Xmx3G` and it hasn't happened since.
- ![image](https://gyazo.com/3752b8f89b05e2878af5620fac2edfbe/thumb/1000)
    - I was able to get to semi-automatic collection, for some reason the villagers won't increase, and when they do, I'm going to lock them up and put them to work.
- Someone who likes decorative architecture updated the base.
    - ![image](https://gyazo.com/631a684c307653affdba724673159fab/thumb/1000)


2021-09-13
- Reduce the frequency of dynmap updates.
- I learned about [Slimefun](https://github.com/Slimefun/Slimefun4), put it in, it is an industrialization plugin that adds generators, etc.
    - If you're not a new user, it looks like you don't have the guide.
        - You can get it at `/sf guide`.
    - I worked hard to dig clay and make bricks, but I misinterpreted, Multiblock is a device that works by "placing" multiple blocks in the world according to a recipe.
    - It takes experience to unlock the technology tree, and I can't do anything because I just died and lost it. w
        - In JE, the experience from burning cactus in a kamado is the same as gold ore.
            - I planted cacti in the sand here and there.
            - Verified if experience or mado bug reproduced in JE -> did not reproduce.
- It's a pain to attach to screen and put in admin commands and quit/restart.
    - Can't you control it with signals or something?
    - You can do it in SIGINT [How to stop PaperMC when not in console - Issue #1757 - PaperMC/Paper - GitHub](https://github.com/PaperMC/Paper/issues/1757)
:

```
$ ps -a | grep java
$ sudo kill <PROCESS_ID>
```

- Enchanted table was made at the base! And lots of cows and sheep.
- The automatic drowning chicken slaughtering equipment used in BE does not work in JE.
    - Item floats and is not sucked up by hopper see [[Micra's Chickens]].
- Micra has a feature [RCON](https://wiki.vg/RCON) that sends packets and executes commands.
    - Client Implementation: [https://github.com/Tiiffi/mcrcon](https://github.com/Tiiffi/mcrcon)
- You can automatically restart java by wrapping its startup in a bash while [src](https://raw.githubusercontent.com/Zachoz/CrashPrevention/master/start.sh).
- Configuration files are now Github managed.
    - Enable-rcon=true` `enable-rcon=true` `rcon.password=XXX` in `server.properties` with RCON also turned on
- ![image](https://scrapbox.io/files/613edb268b15b5001d7dc906.png)

2021-09-14
- They built a Slimefun research facility next to our base.
    - The equipment is bulky and growing rapidly, so it is right to make it in a form that can be expanded.
    - First wooden, but fires broke out because of the fire.
- They built an automatic sapling collection plantation.
    - ![image](https://gyazo.com/673abd87cf0c4da5cdb9b21f4b8493d4/thumb/1000)
    - Plant when you get it. Birch and oak are OK.
- ![image](https://scrapbox.io/files/613fb818832489001d5044f2.png)

2021-09-15
    - [[Mike's Cactus]]
    - Building an automatic cactus harvesting farm on top of the lab or on a farm.
        - →We decided to do it on the farm because it's not safe to use water on the lab and wipe out the Redstone circuit in the event of an accident.
    - stackable
        - Except on the ground floor, you don't have to use the hopper, simply drop it through the hole and it goes into the hopper below.
- They created an experience trap.
- Mass production of cacti in the capital -> convenient to sell them to the villagers and turn them into emeralds, since baking them in the kamado produces a large amount of green dye.
- ![image](https://gyazo.com/4b18b963081a93239605b93b5e740e34/thumb/1000)
- Chest can no longer be placed in [Lockette](https://dev.bukkit.org/projects/lockette): `illegal chest removed`.
    - Large Chest Relationship [src [https://github.com/Acru/Lockette/blob/ac6ad1ef6d8ca5848f49135a18679cf9d0773136/src/org/yi/acru/bukkit/Lockette/](https://github.com/Acru/Lockette/blob/ac6ad1ef6d8ca5848f49135a18679cf9d0773136/src/org/yi/acru/bukkit/Lockette/) LocketteBlockListener.java#L386]
    - Uninstall and deal with the problem without paying the cost of determining the cause.
- Horse moved wrongly problem
:

```
[01:16:18 WARN]: Horse (vehicle of XXX) moved wrongly! 0.2619578421472575
[01:17:18 WARN]: XXX was kicked for floating too long!
[01:17:18 INFO]: XXX lost connection: Flying is not enabled on this server
```

    - It's strange that I get a log saying I'm going too fast on horseback, but then a second later I get kicked for flying, which makes me think I was just riding a horse.
    - changed spigot option: [Server spaming moved wrongly/tooquickly | SpigotMC - High Performance Minecraft](https://www.spigotmc.org/threads/server-spaming-moved-wrongly-tooquickly.237103/)
    - Pipes and autocraft are now included while rebooting.
- [[Transport-Pipes]] is very good.
    - The automatic sorting, which is forced to be achieved by turning hoppers and droppers on and off with redstone, would be compact without being too noisy or heavy.
    - The pipe material asked me if I wanted to download it when I started it, if I didn't put it in, would this happen?
        - ![image](https://gyazo.com/16f6c2cb4f567fa6aa0c87c3cd680f4f/thumb/1000)
- Chicken slaughtering equipment: "When they grow up, use the button on the side to let the water out, wait 20 seconds or so and they all drown, then drain the water and collect the items".
    - With BE, it was just fine to leave the water on the half block and drown from the ones that grew up on it, but with JE, the items float above the water because of the jittery swim and die in the water, and the hopper can't suck them up.
- Slimefun
    - Explosive pickaxe (Explosive Pickaxe) researched but not enough materials to make it.
- Problem with automatic backup not working.
    - `[07:40:51 INFO]: [DriveBackupV2] No backup method is enabled`
    - > DriveBackupV2 is a plugin that aims to provide an extra layer of security to your data by backing it up remotely.
    - I decided to save it to Dropbox.
        - If for some reason the server disappears, there is save data within an hour, so it can be recovered.
- Twitter
    - > [nishio](https://twitter.com/nishio/status/1438069685338083332): What do you recommend a Mac user use nowadays to send or get files to a remote Linux machine?
        - > (typing the scp command in the terminal and thinking "isn't this the old fashioned way?" I think.)
    - > [nishio](https://twitter.com/nishio/status/1438371395839295488): I didn't explain the use case for this, so I got a lot of different opinions, but when we talked about putting the jar of the plugin on the Mycla server, I concluded that it was a good idea to add it to VSCode's I opened it with Remote Explorer and was able to add it with a familiar view, editing the configuration file was easy, and we concluded that we could centralize the configuration management with git, which we had originally done.
- Java option: [Tuning the JVM – G1GC Garbage Collector Flags for Minecraft](https://aikar.co/2018/07/02/tuning-the-jvm-g1gc-garbage-collector-flags-for-minecraft/)

2021-09-16
- How do I decide when I want to restart the server at an appropriate time, even though I'm not in a hurry?
    - →I got the idea of periodic automatic reboots.
    - Automatic restart at 16:00 on weekdays, no restart on weekends except for emergency maintenance
        - I'd like to "reboot only when there is a configuration update," but that comes later.
- I was able to exit and restart via RCON, but rather the problem with the above start.sh is that "the only way to stop the restart is for a human to SIGINT again within 5 seconds of the Java process termination..."
    - You'd have to be a terminal observer to do something like that.
    - Examining conditional branching in bash
:

```
$ [ -f "autorestart" ]; echo $?
1
$ touch autorestart
$ [ -f "autorestart" ]; echo $?
0
```

    - If the `disable_restart` file exists, it is not restarted.
bash

```
if [ -f "disable_restart" ]; then
    break
fi
```

    - Find out how to write cron...
cron_settings

```
30 15 * * 1-5	/usr/local/bin/mcrcon -p <PASS> "say The server will reboot in 30 minutes!"
55 15 * * 1-5	/usr/local/bin/mcrcon -p <PASS> "say The server will reboot in 5 minutes!"
0  16 * * 1-5	/usr/local/bin/mcrcon -p <PASS> "stop"
```

        - It now reboots at 4pm on weekdays with a 30 minute and 5 minute warning.
- [[Transport-Pipes]] can be used to fill the kamado with cactus and fuel.
    - The main task of the hopper, "sucking up items from the world," can only be done by the hopper.
    - It's like forcing the hopper to change from doing a pipeline thing to a straightforward pipe.
- It would be nice if we could notify Mattermost of the completion of the reboot or something.
    - Discord had it [discord-webhook](https://www.spigotmc.org/resources/discord-webhook.84489/)
    - [DiscordSRV](https://www.spigotmc.org/resources/discordsrv.18494/)
        - Notification of login/logout/death for each user and server stop/start
        - Discord and Micra's respective chats are supposed to be relayed, but they are not, cause unknown.
        - → 2021-09-19 There was a statement that LunaChat hooks need to be disabled in DiscordSRV settings because they clash when used with LunaChat at the same time!
- I just want to get 20 seconds of water out of the chickens after they've been growing for 20 minutes for slaughter.
    - I was told that could be done with a daylight sensor.
        - A day in the microwave is 20 minutes.
        - Shorter time than item despawn if water is released only during the highest signal strength in clear weather.
    - How to make a pulse edge detection circuit in a Redstone circuit?
        - I was told I could get the rise and fall just by looking at the observer.
    - Now we have automatic slaughter of chickens.

2021-09-17
- Slimefun There is a nickel that can retrieve the sponer so we can relocate what we find to our base.
- [Eternal Light](https://www.spigotmc.org/resources/eternal-light.50961/) Warnings displayed when it is dark enough for monsters to spawn.
    - The nether is so spicy that placing torches at normal intervals doesn't help the wanderers.
- Slimefun: Industrial Miner, I put 1 coal in the fuel for now, it should only run for 8ore minutes, but I thought it was running all the time, it seems it was taking coal by itself and kept mining, I got 98 pieces!
    - I moved it twice in the same spot and got nothing the second time, so it looks like I'm digging to bedrock at 7x7.
    - Amazing! Coal gulp! I guess, but it consumes 4 stacks of coal to make the synthetic diamonds needed for the creation of the other tools, so it's more in and out...
- ![image](https://scrapbox.io/files/6144cbbfdfb9c0001d3fd878.png)

2021-09-18
- Slimefun, studied an axe that can take a continuous piece of wood in one piece.
    - Convenient because it can cleanly take out trees with complicated shapes.
    - The dense forest around the base was thinned out to create a large chest full of wood piles.
- [[Transport-Pipes]], understanding the behavior of craft pipes.
    - Copper iron gold, coal, redstone, and lapis lazuli placed in the automatic sorting machine are now automatically compressed into blocks before being stored.
- Slimefun Explosion pickaxe, useful for digging underground with good visibility as it can dig 3 squares at once, but its durability is quickly depleted... I had a hard time making it... I guess I'll hold off until I can make a repair device.
    - Axes last longer
- Slimefun I built a pipeline to make gold ore from stone so that I don't have to grind it.
- When I planted a tree by the lava breeder and said to myself, "Now I can make all the charcoal I want," the lava ignited the leaves and caused a huge fire!
    - Good thing the lab is in a fireproof building...
    - I wonder if it would be safe if I put the lid on it.
        - →I think the fire is coming out of the cauldron below.
    - I've been keeping it by the river to limit damage in the event of an accident, but I'd rather keep it indoors where it's fireproof.
- I'm doing research on Basic Circuit Board and seeing how to make it and I'm like "eh..."
- What are some of the continuous operations you would like me to do on an abandoned account? →Round stone maker
    - I researched and built a round stone device [ref](https://zenzenzenchan.com/minecraft-cobblestone-auto-farm/).
    - Only long press, not continuous press.
        - PyAutoGUI
            - > [nishio](https://twitter.com/nishio/status/1439283282626039809): I'm installing Python on my gaming PC because this PyAutoGUI thing looks interesting. I've not built a Python environment on Windows in how many years?
            - > [nishio](https://twitter.com/nishio/status/1439283698919100417): Ctrl+d and say "Hey, I can't exit!
            - enter with pip
python

```
import pyautogui
import time
time.sleep(5)
pyautogui.mouseDown()
```

            - easy
    - Supply pickaxe
        - If left unattended, pickaxes break rather quickly.
            - A stone pickaxe breaks in a little over 3 minutes, not twice as long as steel, and more than 10 times as long as diamonds.
        - Since automatic crafting is possible, why not just make and throw them on a regular basis?
- ![image](https://scrapbox.io/files/614636760e598200232f6e01.png)

- [[Micra JE Diary week2]]
---
This page is auto-translated from [/nishio/マイクラJE日記](https://scrapbox.io/nishio/マイクラJE日記) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
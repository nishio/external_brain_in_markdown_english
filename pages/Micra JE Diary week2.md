---
title: "Micra JE Diary week2"
---

from  [[Micra JE Diary]]

2021-09-19
- composter
    - Putting in unwanted crops will turn them into bone meal.
    - Can be automatically processed and collected by hopper
- ![image](https://gyazo.com/cd9b38168373f9bf388afc15d7d74058/thumb/1000)
    - I built an observation tower to view the scenery.
        - I don't think you get the idea at all, but the front landing gate, it's an M!
            - ![image](https://gyazo.com/e03de537931db08d844d8e00132c631b/thumb/1000)
    - ![image](https://gyazo.com/1dd8ea3ba111abcac26df1d8e9a7e663/thumb/1000)
- skin (e.g. alternative look and feel for interface of a program)
    - I've never played with different skins, but since they were all non-default skins, I decided to change mine.
    - I could have made it at [https://minecraft.novaskin.me/#](https://minecraft.novaskin.me/#)
    - I don't have a particular idea of what I want to do, so I tried on clothes that I would normally wear. w
    - ![image](https://gyazo.com/d64736b2460b59fd7b4ee6359d497d09/thumb/1000)
- I was looking for a solution to the fuel shortage, and I found an endless supply of carpets to use as fuel. w
    - [https://yotsu-cra.info/mugen-kamado](https://yotsu-cra.info/mugen-kamado)
- pumpkin
    - If it's in BE, I've made a rail type one and this one for a tower, but I'm not sure if it would work in JE.
    - [https://kyoukura.net/automatic-melon-pumpkin-farm](https://kyoukura.net/automatic-melon-pumpkin-farm)
- The JE version of the farmer only recognizes fields within a certain distance from the composter.

2021-09-20
- F3+G displays chunk boundaries, useful
- I zipped the entire server directory to run it in creative mode on hand, unzipped it on the Mac, and it worked normally.
- About the mechanism that emits pulses at regular intervals
        - [[10x low-speed logic analyzer]]
        - [[Piston Loop]]
    - JE's adhesive pistons will "pull off".
        - When the signal is 1T, blocks that are attached to each other are separated and blocks that are far apart are attached.
        - This can hold one bit of information.
    - Mechanism to hold one bit of information by stopping the clock circuit with a repeater lock
        - The clock circuit is 2 delays with a torch and repeater, so the signal needs to be 2 ticks long.
            - I don't think the observer that gives a one tick signal is user friendly.
                - And a one-tick signal can't be reversed with a torch.
    - The comparator delays the signal one tick while maintaining the signal strength, so the dust will continue to turn until the strength drops to 0.
            - [[Mysterious behavior when 1T pulse is put into comparator]]
        - When extending the pulse width with a [[comparator loop]] of length N, the comparator loop must be filled with pulses of length N or longer to begin with, and if this is done, the pulse width can be extended by a factor of 6.
            - At 1-4, you can delay it with a repeater and double the length with a wired OR.
            - If we wanted to generate a 40-minute pulse with a comparator loop, we would need to line up 4000 comparators and put in 400 seconds of input, he said.
    - As for multiples of 20, a daylight sensor can be used for compactness.
- The area around the base was getting slow, so I built my own test site away from the base.
    - We wanted to do the tree planting in a large flat space.
    - ![image](https://gyazo.com/1bbd194a0fa1bc3c5f5a49c75d30ea77/thumb/1000)

2021-09-21
- The first android in the world
- Binding a command to a hotkey, I thought this would do it, but it didn't, why?
python

```
>>> import keyboard
>>> keyboard.register_hotkey("ctrl+j", keyboard.write, ("/jumpto\n", ))
```

- They built an automated pumpkin and watermelon machine.
- I left him in a base that wasn't properly enclosed and he died and lost everything.

2021-09-23 Autumn Equinox
- ![image](https://gyazo.com/2e94d48d28597bb31b8c8d2dade60f9b/thumb/1000)
    - He's doing research on afforestation and chicken automation.
- Slimefun's Infused Magnet handy
    - Crouching attracts items around you.
    - When you do forestry work, paraphernalia items will fall around you, making it easier to collect them.
    - I was thinking of making an Infused Hopper for automatic shearing wool collection and made it as a material for that, but a regular hopper is sufficient for the current situation.
        - Style with 6 hoppers pulled and pressure-sensitive plate in the middle
- I fell into a deep hole and died, so I complained and they gave me a pair of slime boots, Slimefun's Magic Armer.
    - Jump enhancement, fall damage nullification, this is useful.
    - Can jump 6 squares.
- Chicken device completed.
    - ![image](https://gyazo.com/fa230997a34f9f7c79d1e4c643fb1221/thumb/1000)
        - [[Micra's Chickens]]
- I left him in the experience trap for 6 hours and he was at level 140.
    - I'm putting out about 10,000 exp in an hour, 167 exp/minute, which is reasonable considering I'm taking down a 10 exp blaze every 3-4 seconds.
    - The cactus kamado is 6 EXP/minute, which is an order of magnitude higher. The advantage is that it accumulates even when the user is not there, but the cacti from the time when there was no fuel are overflowing and disappearing from the chest. It's difficult because there are waves of demand on the human side. I want experience, not burned food, so I can't just put a bunch of kamados in parallel and burn them all at once (I'd have to collect experience one at a time).
    - I still think it's a good idea to go to the traps often, and if my math is correct, I'll be at level 50 in 30 minutes.

- Wow, 5 large chests of blaze rods have accumulated.
- I thought I couldn't do batteries, but there are two types of objects named Copper Ingot, the original and SF...
- The armor craftsman who sells diamond boots and leggings, I had mistakenly thought he only sold those two types of equipment and raised a second one, but in JE he sells upper body equipment at the level above that...
- I built a GPS GEO scanner, but it doesn't work with all these...
    - I guess the two choices are to develop the GPS satellite network sufficiently, or not launch satellites and use them right next to each other.

- Lack of Iron Dust
    - GEO Miner, ore will be available.
        - →The one that takes uranium and stuff.
    - Advanced mining equipment can take the ore block as it is.
        - Two dusts can be obtained from the ore block.
        - Mining with a lucky pickaxe? Even with 3 lucky pickaxes, it's only doubled, so it's no different than unloading a block of ore, and it's better to do it as a block of ore to avoid the hassle.
            - I'd never heard of the good luck effect on watermelon harvesting before.
    - If it can be powdered from iron ingots, there is a route called the golem trap...
        - > Additionally, crushing an Iron Ingot in an Electric Ingot Pulverizer produces one piece of Iron Dust.
            - You can make it from ingots.
    - Proposal to buy a golem sponer at /shop command.
        - Save $1,000,000 and you can buy an Iron Golem Sponer at the shop.
        - I'm still on the default settings, but I had to be in op to purchase.
            - ![image](https://gyazo.com/22f7511c0c588c509163172a89d559ed/thumb/1000)
            - I don't know where to fix the settings.
                - Okay see [[EconomyShopGUI]].
        - It's hard to know what to sell.
            - Green dye, 3 cents Selling a full large chest, about $100
            - Blaze Rods for 231.5 large chests
            - That's $23 for a brick block.
                - (After selling the surplus clay to the villagers.)
            - Wool $7 more than blaze rod $1.25
                - 2126 stack...

- golem trap
    - Golem spawn conditions are much different in JE and BE.
        - [Tutorials/Iron golem farming – Official Minecraft Wiki](https://minecraft.fandom.com/wiki/Tutorials/Iron_golem_farming)
        - ![image](https://gyazo.com/4fc56a4d5e9058b4055c623a05c943df/thumb/1000)
            - [https://zenzenzenchan.com/minecraft-iron-golem-farm-new-version/](https://zenzenzenchan.com/minecraft-iron-golem-farm-new-version/)
        - JE's golem traps don't tell you to "get 100 squares away from the village".
    - Golem traps, hitting a struggling golem in the lava will be considered as killing it, and it will drop Slimefun items.


2021-09-24
- Since dynmap outputs an image to the local file system for each chunk, it may be possible to join these together into a single image.
- I can command a re-rendering of the specified range, so maybe I can cron it early in the morning.
- Transport Pipe, squatting and clicking the wrench on the side of the pipe to turn on/off the connection in that direction
    - There are per-user rendering settings.
        - Only one of them had the setting changed to VANILLA, the others were MODELLED.
        - One person had a problem with the pipe not showing up, probably because of this.
- Golem trap, I left it overnight, but it didn't flow well and I only got one stack.
    - Now we can raise a village tool smith, the age of infinite diamond tools.
    - It's too inaccessible, so if you get a golem sponer in the future, you might want to put it in your main base, that's where you'll use it.
- Diamond weapons, armor, tools, all can now be bought from villagers.
- Pipe out the artifacts and the lava bucket bucket will remain.

- Pipe Explosion Demonstration
    - [https://scrapbox.io/files/614d5ad0389df0001d103e8b.mp4](https://scrapbox.io/files/614d5ad0389df0001d103e8b.mp4)
    - When items above a certain level enter the pipe, it explodes.
        - 20 by default
        - Balance between the default of one sink, which does not occur, and the options, which may occur depending on the structure of the pipe.

2021-09-25
- I decided to trigger dynmap with cron.
    - We started to re-render the area around the base with dynmap at 6am every day.
    - ![image](https://gyazo.com/4858b793f6c736e6027476859560e585/thumb/1000)
    - ![image](https://gyazo.com/e4dcfef99c12edd58d9953749f13d679/thumb/1000)
    - [[Create a large image by joining dynmap tiles together.]]

2021-09-26
I knew, vaguely, that the Tier 1 GPS Transmitter could not do a GEO scan with one...
- If I build a Tier 2 satellite and put it at Y=125, it will be just enough, but GPS satellites are still needed at higher altitudes.
java

```
public int getMultiplier(int y) {
    return y * 4 + 100;
}
```

- [src](https://github.com/Slimefun/Slimefun4/blob/master/src/main/java/io/github/thebusybiscuit/slimefun4/implementation/setup/SlimefunItemSetup.java#L1846)
- Then we found out we needed four Tier 1s to make a Tier 2, so we ended up installing three Tier 1s at 200 altitude.

Programmable Android is ready!
- ![image](https://gyazo.com/e62323a046207ecce1de3d9060822a49/thumb/1000)

They mine obsidian or not in one second without mercy, they are not affected by gravity, they stop instead of going forward if the destination is lava, they are smart! And humans are not smart.
- [https://scrapbox.io/files/614f531e398a2f002270013b.mp4](https://scrapbox.io/files/614f531e398a2f002270013b.mp4)
- Rest assured, little this is a parallel universe. No androids sunk into lava early in life!

Engaged in the humble labor of obtaining one round stone per second.
![image](https://gyazo.com/16fd8d06e0b1f343fa592d91d31bdef7/thumb/1000)

![image](https://gyazo.com/421282cca9dbe33e2b6735d6bdb2c1b7/thumb/1000)
- Is that how the world perceives it...
- I want to do conditional branching!
- [here [https://github.com/Slimefun/Slimefun4/blob/master/src/main/java/io/github/thebusybiscuit/slimefun4/implementation/items/](https://github.com/Slimefun/Slimefun4/blob/master/src/main/java/io/github/thebusybiscuit/slimefun4/implementation/items/) androids/ProgrammableAndroid.java#L700], increase the program counter by 1, get instructions, execute, and repeat... (wait! Wait.
- Maven
    - [https://maven.apache.org/install.html](https://maven.apache.org/install.html)
    - ![image](https://gyazo.com/260586b2c7fb45cadca4cb32e334853e/thumb/1000)
    - At least I was able to build w
- We could add our own commands.
    - ![image](https://gyazo.com/b1d49674344f53f5c3cee549e8f67a12/thumb/1000)
- The original language specification is a list of instructions that do not take operands, so I'm thinking that extending from here would be a bad (though not impossible) foothold.
- I made an error and my android disappeared from WW.
    - Development environment where writing a buggy program will kill the android, too high a hurdle.
:

```
[12:15:42 ERROR]: [Slimefun] X: -56 Y: 63 Z: -239 (PROGRAMMABLE_ANDROID_MINER)
[12:15:42 ERROR]: [Slimefun] has thrown 4 error messages in the last 4 Ticks, the Block has been terminated.
```

    - `ImportError: Cannot import site module and its dependencies: No module named site`
        - jython, the normal version has the libraries in separate files and you need to put them in the right place. There is a separate jython-standalone that contains everything.
- Python can now be run in Programmable Android in Minecraft (PaperMC+Slimefun)!
    - ![image](https://gyazo.com/3c2874d8a7d6c3b3609124bdf9744f58/thumb/1000)
    - I've made Programmable Android programmable in a decent language, but it's not a decent development environment to program on the Micra GUI, so if I develop it in a decent VSCode or something and push it to Github, the behavior of the robots in the Micra world will change. I'd like to see it (wait.

2021-09-27
- [https://github.com/ammaraskar/pyCraft](https://github.com/ammaraskar/pyCraft)
    - > Minecraft-client networking library in Python.
- Minecraft Becomes a Web of Voxels [PDF](https://github.com/kengonakajima/blog/blob/master/articles/minecraft_web.pdf).
- [wiki.vg](https://wiki.vg/Main_Page)
- [https://prismarine.js.org/](https://prismarine.js.org/)
    - If you set `online-mode=false` in `server.properties`, you can log in with a bot account without Mojang authentication.
    - However, user data changes from the time when it was true, and belongings, progress, Slimefun research, etc. are reset.
    - That was unacceptable, so I put it back once.

:

```
[03:51:18] [Craft Scheduler Thread - 243 - DriveBackupV2/INFO]: [DriveBackupV2] Uploading file to Dropbox
[03:51:28] [Craft Scheduler Thread - 243 - DriveBackupV2/INFO]: [java.net.SocketException: Connection reset by peer, java.net.SocketException: Connection reset by peer]
[03:51:28] [Craft Scheduler Thread - 243 - DriveBackupV2/WARN]: java.net.SocketException: Network is unreachable
```



[https://github.com/PrismarineJS/mineflayer](https://github.com/PrismarineJS/mineflayer)
`Error: This user does not have any items on its accounts according to minecraft services.`
- I can't have two logins on my account at the same time, so I created another MS account.
- But you can't play on that account because it hasn't been purchased yet.
    - Bought.
![image](https://gyazo.com/9e9d48a20ead33c57df3d42ce99ca29f/thumb/1000)


[https://github.com/PrismarineJS/mineflayer-pathfinder](https://github.com/PrismarineJS/mineflayer-pathfinder)


[https://scrapbox.io/files/61516cc5934d12001d0dc045.mp4](https://scrapbox.io/files/61516cc5934d12001d0dc045.mp4)

[https://scrapbox.io/files/61517e27f11b61001db4a93b.mp4](https://scrapbox.io/files/61517e27f11b61001db4a93b.mp4)

![image](https://gyazo.com/b1796cf62428d8b53723376c35274beb/thumb/1000)



![image](https://gyazo.com/25774d0815d3c12ca08229f1cc8a485b/thumb/1000)
![image](https://gyazo.com/e23e7109fc90dfb2e5df389dc392f48b/thumb/1000)

![image](https://gyazo.com/71fa6273e7c7459ab2710ac4356b5789/thumb/1000)
[https://scrapbox.io/files/6152987f2c636e001dcaadf6.mp4](https://scrapbox.io/files/6152987f2c636e001dcaadf6.mp4)

![image](https://gyazo.com/0e26236c02593225e085385c87518d3d/thumb/1000)


![image](https://gyazo.com/d09ffc2f2f11afee262c6dadeb550175/thumb/1000)

[https://twitter.com/nishio/status/1443221023667605513](https://twitter.com/nishio/status/1443221023667605513)


![image](https://gyazo.com/4d09c1ee6255bcf413a891f2004beffb/thumb/1000)
![image](https://gyazo.com/e1a3d8df97927087d14674b439058d52/thumb/1000)
![image](https://gyazo.com/6bfed79898da4ab4bdfac7299d9dd6fe/thumb/1000)

[https://minecraft.fandom.com/wiki/Head](https://minecraft.fandom.com/wiki/Head)

[https://minecraft.fandom.com/wiki/Tutorials/Amethyst_farming](https://minecraft.fandom.com/wiki/Tutorials/Amethyst_farming)

[https://youtu.be/eYmUBfXan9Y](https://youtu.be/eYmUBfXan9Y)

[https://minecraft.fandom.com/wiki/Air](https://minecraft.fandom.com/wiki/Air)

[https://github.com/kii-chan-reloaded/GeneticChickengineering](https://github.com/kii-chan-reloaded/GeneticChickengineering)

[https://github.com/Sefiraat/EMC2](https://github.com/Sefiraat/EMC2)

- [[Micra]]

---
This page is auto-translated from [/nishio/マイクラJE日記week2](https://scrapbox.io/nishio/マイクラJE日記week2) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
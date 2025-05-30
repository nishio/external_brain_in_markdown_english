---
title: "Automatic sorter that can adjust the number of items stored by type"
---

Minecraft automatic sorter that allows you to adjust what and how many stacks to store for each type of item.
- ![image](https://gyazo.com/d5cf9ccd7f1a01d1d713eef23bae10d1/thumb/1000)
- One chest, one type, is too scanty.
- I want to manage up to 54 types in 1 large chest.
- You can do things like, "Let's save only five stacks of sand and automatically glass the rest."

Basic Structure
- Stack the parts vertically, "If you can put it in the chest, put it in; if you can't, pass it to the hopper below."

## Chapter 1: Using the hopper for storage
.
- What you can do in this chapter:.
    - Automatic sorter for up to 5 stacks, can be connected
    - No need for Redstone.
    - ![image](https://gyazo.com/41b11f8e130ed334619d96c4c1f73fb9/thumb/1000)

Hopper sucks and feeds one object with 8 ticks
- A tick is 0.1 second.
    - (There are two types of redstone ticks and game ticks, but we will only talk about redstone ticks here.)

If a hopper X containing one item has a hopper Y below it that can suck up that item, the sucking up of Y takes precedence over the feeding of X.
- So in this figure, if five stacks of carrots are placed in the top chest, none will be placed in the right chest and all will go into the bottom hopper.
    - (Some of the world's explanations for the 50/50 split are based on putting things directly into the hopper.)
    - ![image](https://gyazo.com/9e885c12b45d5c2a283eb674fd14121e/thumb/1000)

The simplest automatic sorting is to use this "lower hopper" as a chest that holds only 5 stacks.
- It sucks up only when it can, so if you fill the frame with things you want to put in beforehand, it will suck up only those things.
- Does not require Redstone.

It can be extended as many times as you want.
- ![image](https://gyazo.com/16001efd9da1ba2f01feb8b87e5d5c85/thumb/1000)
- The chest on the right holds "stuff that didn't fit anywhere else".

Up to 5 stacks with 2 hoppers per unit, can be done with 5 of the same type or 5 of each different type.
- This is particularly effective in the shopping area, where what villagers buy can be stored in a hopper near the villagers.

If you want to reduce the amount you receive by more than 5 stacks
- Just put in something that doesn't flow, or doesn't get stuck, or is plentiful and can get stuck.
- Many explanations in the world write "named stick," but that is because it must be something that does not flow when a comparator is used. In this case, there is no need for a "named stick" at all because a comparator is not used
- For example, if you are short of resources in the early stages, you can use spider's eyes, which are "things you want to keep for future use but don't plan to use in the immediate future," or soil that you have in abundance.
- No stacks of stone tools and other tools that you had to buy to grow the tool forge, and if you have enough iron to use the hopper for automatic sorting, you don't make it anymore, so it's suitable for something that fills in the gaps.

## Chapter 2: Redstone control of hopper and storage in chest
- What you can do in this chapter
    - Automatic sorters with 54 stacks per unit
    - Can also do "54 types, 1 stack each."
    - Redstone required

Hopper will not suck or send out a redstone signal when it receives a redstone signal.
- However, it can be sucked out by the hopper below.

- So the upper and lower hoppers are turned on and off with redstone to achieve "if you can put it in the right chest, put it in, if you can't, pour it into the lower hopper".
    - ![image](https://gyazo.com/7aba383e8c37b799a297d354ae84af16/thumb/1000)
    - Explained in two tiers, but can be connected up and down.
    - If a dropper elevator is built, it can be connected in a myriad of lateral directions.
- The first chapter's method was "only 5 stacks", but this one increases to 54 large chests per unit.
- First write about the principle of Redstone Signal for that purpose.

### Redstone Signal Transmission
.
- Blocks strengthened by repeaters can signal to adjacent blocks
    - Repeater = Redstone Repetition Device
    - Strengthening = to make a state in which strong power is transmitted, a term coined by <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>.
    - However, this cannot be done with glass or other impermeable blocks.
    - Strengthened blocks transmit signals in six directions, including up and down
- Powder can signal connected blocks.
    - Powder = Redstone powder
    - This is a different state from the aforementioned strengthening.
        - Activation, also called "weakly powered state"
    - Connection is not adjacency.
        - Powder must be facing or on top of the block.
    - The torch attached to the activated block goes off.
        - Torch=Redstone torch
        - This allows for logical negation.
        - ![image](https://gyazo.com/5c663359642c232e55b2c92b7565271f/thumb/1000)
        - ![image](https://gyazo.com/7fa8154f53866171d96db356cd614ce5/thumb/1000)

### V-shaped clock
.
- Placing the blocks in a V-shape makes a compact clock circuit.
    - ![image](https://gyazo.com/b9e3281d34a9317cc86d1d060c96bc37/thumb/1000)
- This is referred to as a V-shaped clock in the following
- operating principles
    - Let the three blocks be, from left to right, A, B, and C.
        - First, the torch powers A.
        - Thereby, one tick later, the repeater strengthens C
        - C is strengthening and activates the powder below.
        - Powder's connecting B is activated.
        - One tick later the torch on B goes off.
        - The repeater input is turned off and C is turned off one tick later,
        - Torch turns on after 1 tick.
- So this loop keeps pulsing 2 ticks on, 2 ticks off.
    - The switch stops the pulse by keeping A constantly on.
[https://scrapbox.io/files/6130f76447a283001d370dc4.mp4](https://scrapbox.io/files/6130f76447a283001d370dc4.mp4)

- At first I forgot about the torch delay and thought it was one on, one off.
        - [[Logic Analyzer @ Micra]].
- After this, we'll pulse 5 ticks into the hopper, so we'll set the repeater delay to 4 ticks.

### hopper behavior
.
- Hopper sucks up the top on the first tick and feeds it out on the fifth tick
    - Some sites say it's once every 8 ticks, but as of 2021-09-04, at least in BE, it's not.
        - [[Verify behavior of hoppers side by side]] I did.
- So we need to run the hopper for at least 5 ticks.
    - If the hopper has stuff on top, it sucks it up first, then feeds it out.
        - So if there is always something on top, such as a chest placed on top, it will suck it up even when it is time to feed.
        - This way, there is always one item left in the hopper, and no matter what timing you stop, you cannot prevent "items that should not flow down from flowing down".
    - So we need to limit the flow to "1 in 10 ticks" with a dropper.

### adjustable capacity sorter
.
- ![image](https://gyazo.com/7aba383e8c37b799a297d354ae84af16/thumb/1000)
    - [https://scrapbox.io/files/613367e8574b8500231b91f0.mp4](https://scrapbox.io/files/613367e8574b8500231b91f0.mp4)
    - Items in the top left input chest flow through the hopper, those that fit in the top chest are in the top, and those that do not are in the bottom chest.
- structure
    - 5 on 5 off signals are being sent from the off-screen V-shaped clock.
    - The lower hopper is conveyed by reversing with a torch
    - Tell the upper hopper by strengthening the block behind it with a repeater.
        - Is the bottom of the repeater glass to keep the signal from being transmitted down? To prevent the signal from being transmitted from the torch to the side?
            - Maybe it doesn't have to be glass because I haven't found a case where it would cause a problem.
    - Both delays are one tick, so they are just reversed signals.
- Droppers flush items once every 10 ticks.
    - ![image](https://gyazo.com/f51e3e2c2435a3502623506033c32ab6/thumb/1000)

### Hopper phasing
.
- Hopper sends an item once every 10 ticks, but this timing can't be anytime
- For example, if an item does not reach the first tick where the top hopper is on, but reaches the second tick, the top hopper turns off and the item sucked up there is sucked up into the bottom hopper before it can be placed in the chest. The result is that "items that can be stored in the upper chest end up in the lower chest".
- In this configuration, the dropper is delaying the timing of the dropper's movement across the repeater.
    - Four ticks wouldn't work, five ticks would work.
    - This is of course affected by the length of the hopper
    - So it's better to adjust with repeaters.
    - When it's failing, even if there's room in the top chest, it will go in the bottom chest, so just adjust the top chest so that things go in the top chest while pouring out as many things as you see fit.
- I can now produce it by calculation without trial and error here, see below.

### Extended
.
- The first site I referred to had six vertical rows and two rows with dropper elevators.
    - Made in Survival (Golem traps have already been created).
    - Honestly, I could have 12 large chests 648 stacks of storage.
    - ![image](https://gyazo.com/a5532225270fcbdd10405f2954c9d6da/thumb/1000)

Hopper phasing 2
- write later
    - [[Why is a 4T delay not acceptable and a 5T delay is OK?]]


Chapter 3 Dropper Elevator
A dropper elevator or dropper-type item elevator is a system that transports items upward by stacking them vertically with the dropper's item ejection port facing upward.

There are so many articles that I don't need to explain them here, so I will omit them.
[https://n5v.net/dropper-item-elevator/](https://n5v.net/dropper-item-elevator/)


Chapter 4 Comparator Type Sorter
- Automatic sorting chest that uses a comparator to put in only one type of item.
    - Frankly, I'd rather have a second chapter sorter because it's bulky.
    - And we need lots of comparators.
- principle
    - Prepare a hopper X that cannot be fed out and only sucks up one type of material.
    - Get signal from hopper X with comparator
        - Signal strength depends on the amount of stuff inside.
    - When more contents are added, the signal moves the hopper under the X to suck them out.
        - That hopper is connected to the chest.
    - Now you can put only one set of things in the chest.
- This article explains it in detail.
    - [[Micra](https://minecraft-redstone.com/new-item-sorter/) Easier! Unbreakable New Type Sorter [[Integrated Version]]]

- Advantages
    - The sorting machine in Chapter 2 was one item per 10 ticks.
    - This sorter is 1 item in 4 ticks.
    - So it's good to use this mechanism to suck up dirt, sand, and other things that tend to be in large quantities first.
        - When the soil chest is full, throw it in the trash instead of pouring it into a downstream sorter.
    - What and how much you want to keep depends on your style of play.
        - For me personally, I'm inclined to say "I don't want all the sand to be glass, but 5 stacks should be enough," so I think the hopper-type sorter in Chapter 1 will suffice.
        - Vegetables from automatic farms tend to be in large quantities, so this might be a good way to sort them.


- [[Automatic sorter with adjustable number of storagesdraft]]
---
This page is auto-translated from [/nishio/種類ごとに収納数を調整できる自動仕分け機](https://scrapbox.io/nishio/種類ごとに収納数を調整できる自動仕分け機) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
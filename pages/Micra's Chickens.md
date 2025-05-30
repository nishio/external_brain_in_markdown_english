---
title: "Micra's Chickens"
---

Figures for Chickens
- Dispenser holds 9 x 16 = 144 eggs
- 1/8 chance of being a chick, so about 18 chicks will be produced.
    - A little more because of the probability of multiple animals being born.
- JE would die from dense damage if more than 25 animals per block.
    - They don't seem to die in BE, but the FPS of the game gets worse, so I'd say you should plan on 18 of them.
- 20 Minutes to Adulthood.
- Produces one egg every 5-10 minutes after reaching adulthood
    - So it will take 40-80 minutes to collect and sustain the first 144 eggs.
    - If 18 x 4 = 72 adult chickens are kept in 4 squares and eggs are collected, 144 eggs will be collected and equilibrated in 20 minutes before the chick becomes an adult
        - At this time, 18 chickens will be produced in a little over 20 minutes.

How to kill a chicken
- Easy by drowning in BE.
    - Keep a chick on a half block and place water on the block above it.
    - As adults, they grow taller and their heads go into the water and they drown.
    - You can suck this up in the foot hopper.
- This was not available in JE.
    - Slight gap above the water.
    - Chickens in the water will float wildly, and when they drown in that state, the item floats above the water and cannot be sucked up by the hopper at the foot of the chicken.
    - Submerge and die in about 20 seconds, so if there is a "dispense water and stop in 20 seconds" system, items can fall to your feet and be retrieved.
        - This can (and should) be achieved by combining a hopper and a comparator.
        - Easy with daylight sensor
            - This "time out of the water" should be longer than the 20 seconds required for drowning and shorter than the 5 minutes the item despawns.
            - Sunlight sensor at maximum intensity for less than 5 minutes on sunny days
            - Turn ON only at the highest intensity in the comparator.
            - The observer looks at it and obtains the timing of the change.
            - Now you can safely kill chickens.
            - Rainy days prolong life and so do eggs.

Egg ejection volume control
- Not too lame if you're manually filling the dispenser with eggs, but it's a hassle.
- If you make it so that it is brought in automatically, if you don't stop it properly, it will keep injecting and the chick will die from dense damage.
    - I made two mistakes and killed over 50 animals for nothing.
    - It's not good that the system is designed to make mistakes.
- [[Transport-Pipes]] allows 16 pieces to be transported at once, so turning it on for only 9 seconds is sufficient.
    - The hopper sends one item every 0.4 seconds, so it can be used like an hourglass.
        - Place 25 pieces of sand in the hopper and use the comparator to signal while the item is present.

2021-09-23
![image](https://gyazo.com/fa230997a34f9f7c79d1e4c643fb1221/thumb/1000)
- The end result.
    - Ejects an egg once every 6 seconds.
    - There are 15 repeaters with 0.4 delay.
    - 200 ejections in 20 minutes.
    - 1/8 chance, so that would be 25 animals.
    - Illuminance sensor to produce water once every 20 minutes
    - Eggs are raised 4 squares of adults downstairs and piped in to the dispenser.

- [[Micra]]

---
This page is auto-translated from [/nishio/マイクラのニワトリ](https://scrapbox.io/nishio/マイクラのニワトリ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
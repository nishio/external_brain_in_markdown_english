---
title: "Verify behavior of hoppers side by side"
---

![image](https://gyazo.com/9402527607a49c620f80517a66ee539a/thumb/1000)
- I built a device to check the behavior of the hopper, but unlike the signal, it's slow, so I didn't need to build it this long...
- [https://scrapbox.io/files/61330fa48f412b001d3d8759.mp4](https://scrapbox.io/files/61330fa48f412b001d3d8759.mp4)

I realized that the hopper turns off when the on signal comes on, so to move it around a bit and see how it behaves, I need a "circuit that is always on and makes off pulses of a specified length".
    - Torch the output of [[Pulse generator with adjustable length]] to logic negation.

Observe what happens when you change the width of the pulse.

Hopper sucking occurs at 2 ticks but no feeding occurs.
- The feed does not occur until the 4th tick, and only occurs at the 5th tick.
- At this time, suction also occurs.
    - (This smells fishy, and it throws off the premise of the design.)
- Furthermore, the transmission to the next hopper is the ninth tick.
- ![image](https://gyazo.com/3d3be827250cb8cf42228c523486dbb5/thumb/1000)
From this behavior, if there is enough stuff on the hopper, there is no transition to the "fed but not sucked out" state.
- Controlling this hopper signal alone is not enough to sort.
- It is necessary to create a situation where there is nothing on top of the hopper on the fifth tick.
    - For example, this can be accomplished by droppering only one item every 10 ticks.
---
This page is auto-translated from [/nishio/ホッパーを並べて挙動を検証](https://scrapbox.io/nishio/ホッパーを並べて挙動を検証) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Heavy if you put out a lot of sticky notes."
---

[[pRegroup2020]]
![image](https://gyazo.com/060454e467076e3f23a391a19f8746ee/thumb/1000)

- 100 sticky notes out, heavy at a level that makes it difficult to write by hand.
- It's not like the sticky is moving around, it's just weird that it's so heavy when handwritten.
    - Are you redrawing the whole thing?

- Trying pen input with only about 10 stickies on the screen (the objects themselves are 1000) and the FPS drops to almost 1.
    - It looks like everything is redrawn, including off-screen, during pen input.

- On a PC, I'm talking about "you don't have to put out that many" because I'm trying to reproduce the problem, like 10,000 stickies, but on an iPad, I'm at the point where I'm getting uncomfortable delays at 100 stickies, so this isn't working.

- Handwriting was speed sensitive, so, well, we'll have to separate the canvases.
- Zooming and moving stickies when 100 stickies are displayed is a frequent use case
    - That's the fundamental problem with a stressful situation there.
        - [[Ability to display 100 stickies and zoom without stress.]]
        - [[Ability to display 100 stickies and move stickies around without stress.]]
        - [[Smooth handwriting.]]

- I don't think the machine's performance is inherently lacking.
    - If you use paper.js in a straightforward way, you can't prune branches because paper.js is made to be generic.
    - I think if you build a use case and a tightly coupled system, you'll get the level of performance you're hoping for.
        - In this assumed use case, what the user edits always comes to the forefront, so it would be OK to overlap the canvas to be edited and the canvas to be retained.

- It is still strange that something as simple as "a picture of 100 boxes on the screen" cannot be scrolled or zoomed smoothly.
    - It is necessary to prevent heavy processing from running on touchmove-like events.
    - paper.js on the other hand probably:.
        - Changing the zoom causes the entire object tree to be traversed and redrawn, regardless of whether it is in the screen or not
        - Adding objects redraws them all as well
    - Reason: Because
        - Stickies are heavy even if they are off-screen.
        - Handwriting lags when other objects are unchanged.
            - I'm running a heavy process for adding paths during handwriting.

- [[Imaging at zoom]]
- [[Canvas acceleration]]
---
This page is auto-translated from [/nishio/付箋をたくさん出すと重い](https://scrapbox.io/nishio/付箋をたくさん出すと重い) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
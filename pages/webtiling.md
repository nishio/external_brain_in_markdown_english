---
title: "webtiling"
---

An application that displays web pages in a tiled view
[https://github.com/nishio/webtiling](https://github.com/nishio/webtiling)
- Implementation details
    - Configuration file in JSON (config.json)
    - Window management using [[Electron]] (WindowManager)
    - Tile display function (TileManager)
    - Offset control function (OffsetController)
    - Configuration file loading function (ConfigLoader)

- Start with another config file: npm run start:custom test-config.json
- Save as

![image](https://gyazo.com/9012cfc00fb6de286c64d257d0b3fc44/thumb/1000)
2025-05-04
It's starting to take shape.
- I put Scrapbox and Devin side by side, and there was a gap on the right, so I put YouTube for now.
- Or put something in the bottom half of YouTube.
    - After I did it, I thought that YouTube is not tightly coupled with the work content, so there is no need to bundle it with this system...
- Ability to save browser tab openings at any size







[[Vivaldi]] has a [[tab tiling]] function, but when I tried to use it on [[XREAL One]], I couldn't customize it much.
    - [[Wide monitor support with Tab Tiling in Vivaldi]]
- XREAL One's [[landscape widescreen]] is 3840 × 1080 pixels
    - If you make it 1/3, the center is just right for viewing Cosense, and it's too narrow for doing something with a sidebar like Devin.
    - In the first place, the center is the main work area and the sides are sub areas, so they should be smaller.
        - You can drag and change it, for one thing.
    - When you want to play YouTube on a small screen, just dividing the columns creates wasted space.
        - I wonder if it would be possible to split the columns further up and down only on the sides...
- You can get by with multiple Chrome Window and arrange them in any size you want.
    - But it's interpreted as a separate app in the first place, so it's messed up and returned to the desktop when XREAL is deactivated.

- I casually tossed it to Devin at [[Devin credit used up 4/26]] and it was easy.
- > Electron+BrowserView now has a tool to display multiple web pages with arbitrary tiling()

2025-05-01
- Surprisingly, it's working fine.

2025-05-02
- I did a Google login to get into Scrapbox.
    - It's an unknown application and requires two-factor authentication, that's it.
    - I thought it would be a hassle every time, but the next time I booted up with no problem, I got up logged in.
    - Could it possibly be used for the purpose of having AI read sites that require authentication?
- I'll ask Devin to take care of the details I noticed.
    - [https://app.devin.ai/sessions/cf0a515c5069470d91a821bc291be6b3](https://app.devin.ai/sessions/cf0a515c5069470d91a821bc291be6b3)
    - [https://app.devin.ai/sessions/00598fe10c224efb9542b86c4c61e274](https://app.devin.ai/sessions/00598fe10c224efb9542b86c4c61e274)

---
This page is auto-translated from [/nishio/webtiling](https://scrapbox.io/nishio/webtiling) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Unity + Gear VR development notes"
---

[Unity+Gear VR development notes - Frame Synthesis](https://framesynthesis.jp/tech/unity/gearvr/)
#Unity #GearVR

- About [anti-aliasing
- Recommended by [vrdaveb
    - In [[Player Settings]], set [[Rendering Path]] to Forward.
        - Maybe [[Graphic Settings]]?
        - Already Forward by default
    - Multi Sampling ([[MSAA]]) in Anti Aliasing under Quality Settings
- MSAA is lighter than Image Effects anti-aliasing ([[FXAA]])
- Polygon edges are much cleaner.
- 2x MSAA is almost no cost for Gear VR
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I made it to 8x and it didn't seem pretty.
    - I set [[MSAA]] to disable because I did [[FXAA]], but since you said no cost up to 2x, I set it to 2x.

---
This page is auto-translated from [/nishio/Unity＋Gear VR開発メモ](https://scrapbox.io/nishio/Unity＋Gear VR開発メモ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
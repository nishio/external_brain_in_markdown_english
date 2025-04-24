---
title: "Piston Loop"
---

![image](https://gyazo.com/fc94a82086bbc1ac05a97b23d50c1a6c/thumb/1000)

- I was struggling with how to automate long cycle operations in [[Micra]] and was told.

[https://scrapbox.io/files/61488c6e5d81cb00235bd331.mp4](https://scrapbox.io/files/61488c6e5d81cb00235bd331.mp4)
With this minimum configuration, 20 x 0.4 would be 8 seconds apart.
- We could quadruple the number of repeaters with this shape. So 32 seconds.
- If we increase the size, we can increase the number of repeat customers and the distance they travel, which increases the cycle on the order of squares.


I reversed the signal.
- [https://scrapbox.io/files/6148979f098dc2001decd43c.mp4](https://scrapbox.io/files/6148979f098dc2001decd43c.mp4)

- When reading from the observer, it was difficult to handle the 1-tick signal, so it was changed to read from the basement.
    - Redstone block can turn on powder on top of the block below.
- In this configuration, 60 x 0.5 seconds is 30 seconds.
- If you don't put at least two repeaters, you'll get "the piston can't extend because the piston that's out is in the way.
- 96 seconds if the repeater is increased to 1.6 seconds.

About 20 and 60
- When the direction of movement coincides with the signal direction
    - Two squares in succession at the corner per piston 4 pushes.
    - Therefore, it takes 16 pushes to advance 8 squares.
    - Plus the effect of going around the circle +4 to 20.
    - If each side is increased by one block, each side is increased by 16 pushes, since only one square is advanced per 4 pushes.
- When the direction of movement and the signal direction are opposite
    - One square advance per 4 piston pushes
    - So it takes 64 pushes to advance 8 squares.
    - Plus the effect of circling backwards -4 to 60.
    - If each side is increased by one block, 16 pushes are added.
        - Lag due to increased repeat business +0.4
        - That is, when one side is n $(0.4 + n * 0.4) * (16 + n * 16)$
        - If you want to make a 25 minute timer, one side is 14.

---
This page is auto-translated from [/nishio/ピストンループ](https://scrapbox.io/nishio/ピストンループ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
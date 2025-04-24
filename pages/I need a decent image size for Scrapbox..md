---
title: "I need a decent image size for Scrapbox."
---

Maybe this needs to be verbalized as "what is a sane state of affairs".

not in one's right mind
- ![image](https://gyazo.com/f2e0c356b85d2015cc9e60524f8ca747/thumb/1000)
- The second image is too big.
    - On a smartphone, the screen width is small enough to be decent.
    - ![image](https://gyazo.com/64dffe659b7e940fe2900d92b76b17f4/thumb/1000)
- What you want to have the same width is scaled to have the same height.
    - Then why not `width: 50%`?
    - ![image](https://gyazo.com/ea5ea10e60caa05d6209701cb636017f/thumb/1000)
    - `max-height: none !important`
    - ![image](https://gyazo.com/9c70a56101c32b286913b36ee9968310/thumb/1000)

But on a smartphone, it's small.
![image](https://gyazo.com/ecbfb89a8e850a923a7bd5038e2510d9/thumb/1000)
- Well, that's what happens...

- Should I set max-width to 300px or something?
    - ![image](https://gyazo.com/e16869a50c2dd22a0a1d220ef8ae6d36/thumb/1000)
    - Ah, overriding `max-width: 100%` to poke through when the width is over 100%.
    - `width: 100%`
Conclusion.
- In some use cases, you want to align with max-width instead of max-height.

---
This page is auto-translated from [/nishio/Scrapboxの画像サイズをまともにしたい](https://scrapbox.io/nishio/Scrapboxの画像サイズをまともにしたい) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
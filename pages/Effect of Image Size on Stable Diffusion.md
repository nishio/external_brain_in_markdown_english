---
title: "Effect of Image Size on Stable Diffusion"
---

As for whether the sampling method is [[DDIM]] or [[PLMS]], there is some difference, but it is not so obvious to the human eye
![image](https://gyazo.com/0ed967f2faddaba3bb4b3868949df758/thumb/1000)![image](https://gyazo.com/aa6d3fed9f7d97b07a877b23ea94c4ac/thumb/1000)

Rather, the effect of size is so great that it's a completely different thing.
![image](https://gyazo.com/5c593cd3ca14658dd22190e76bffc88d/thumb/1000)
![image](https://gyazo.com/2ae797fdd1a543c059438c06bf86b94f/thumb/1000)
![image](https://gyazo.com/86e6ad3429432b611f572eb83a41845e/thumb/1000)
![image](https://gyazo.com/0ed967f2faddaba3bb4b3868949df758/thumb/1000)
If the composition is the same even if it is small, I tried the "generate many at high speed at a small size and then select the best ones for higher resolution" approach, but it didn't work at all.

[[LDM]] in [[Stable Diffusion]] does [[diffusion model]] in latent space
- Not a [[super-resolution (e.g., video)]] approach after diffusion modeling in the space of small images
- Perhaps that's why.

---
This page is auto-translated from [/nishio/Stable Diffusionの画像サイズの影響](https://scrapbox.io/nishio/Stable Diffusionの画像サイズの影響) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
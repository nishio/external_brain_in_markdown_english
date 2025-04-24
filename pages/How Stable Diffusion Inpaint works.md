---
title: "How Stable Diffusion Inpaint works"
---

![image](https://gyazo.com/7bbbd2f36bc287afe03cd0b19e6f9ce9/thumb/1000)
- [[VAE]]

![image](https://gyazo.com/f53be72b72b7a24b54c614b70dc8ef89/thumb/1000)

The "function that redraws only the unmasked areas" is a crude explanation for the general public.
- It's not a "don't change anything that's masked, just make the rest of it so that the boundaries add up."
- If you zoom in, you can see the changing mesh pattern on the masked bench.
    - ![image](https://gyazo.com/3555cfd5ad7d03a520c5be77bb59ad93/thumb/1000)

- It is natural that the masked area will also change, because there is not enough dimension in the latent space to hold that detailed information.
- Even if there were no mask and no noise, the image would still be shaky because it's being restored from one-sixteenth of the information content.

---
This page is auto-translated from [/nishio/Stable Diffusion Inpaintの仕組み](https://scrapbox.io/nishio/Stable Diffusion Inpaintの仕組み) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Denoising Diffusion Implicit Models"
---

> Denoising diffusion probabilistic models ([[DDPM]]s) have achieved high quality image generation without adversarial training, yet they require simulating a [[Markov chain]] for many steps to produce a sample. To accelerate sampling, we present denoising diffusion implicit models ([[DDIM]]s), a more efficient class of iterative implicit probabilistic models with the same training procedure as DDPMs. In DDPMs, the generative process is defined as the reverse of a Markovian diffusion process. We construct a class of non-Markovian diffusion processes that lead to the same training objective, but whose reverse process can be much faster to sample from. We empirically demonstrate that DDIMs can produce high quality samples 10× to 50× faster in terms of wall-clock time compared to DDPMs, allow us to trade off computation for sample quality, and can perform semantically meaningful image interpolation directly in the latent space.
[https://arxiv.org/abs/2010.02502](https://arxiv.org/abs/2010.02502)

- ![image](https://gyazo.com/595652fbd6ba206b07df700489c26470/thumb/1000)
- In DDPM (denoising diffusion probabilistic models), "one-step denoising" was learned in a Markovian manner, but in DDIM (denoising diffusion implicit models) it was made non-Markovian.
    - This made it about 10-50 times faster.

[[Diffusion model]]

adversarial training: see [[GAN]]

---
This page is auto-translated from [/nishio/Denoising Diffusion Implicit Models](https://scrapbox.io/nishio/Denoising Diffusion Implicit Models) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
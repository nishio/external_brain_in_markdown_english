---
title: "Variable auto encoder"
---

[[VAE]]
Variational Autoencoder (VAE)
Kingma & Welling (ICLR 2014) “Stochastic Gradient VB and the Variational Auto-Encoder”

[From Variational Bayesian Method to VAE Daichi Mochihashi](http://chasen.org/~daiti-m/paper/vb-to-vae.pdf)
- [[Variational Bayesian]] issue
- You can't derive an EM algorithm without a good shaped distribution.
- The factorization assumption $q(z, \theta) = q(z)q(\theta)$ is strong
Normal [[Auto Encoder]] does not know the distribution of the hidden variable z
Then consider a model where z is a multivariate standard normal distribution
VAE= [[variational approximation]] ＋ [[neural net]]

What is VAE in a nutshell?
    - First there was the auto-encoder, which gave rise to the concept of "latent vectors".
    - If we can sample from this distribution of latent vectors, we can use it in a generative model.
    - However, the raw autoencoder is a set of vectors corresponding to the actual input data, so sampling from it will only yield the data used for training.
    - Here, the distribution of this latent vector is "a simpler distribution (Gaussian distribution per axis?). Variational autoencoder is a stochastic model of the structure equivalent to an autoencoder, using the "variational approximation" that the distribution of this latent vector is "the product of a simpler distribution (Gaussian distribution per axis?)" and is in the form of a Bayesian update.
- I guess you could say that.
- This article points out that "the original paper did not create VAE as a Bayesianization of the autoencoder", which means that the description of the flow as I did is not appropriate.
    - [https://academ-aid.com/ml/vae](https://academ-aid.com/ml/vae)
- pointing out
    - VAE is not Bayesian inference.

[[ELBO]]
- [[amortized reasoning]]
- [[Jensen's inequality]]
- [[Helmholtz machine]]
variable transformation track
- bus-wise
Priority sampling



---
This page is auto-translated from [/nishio/変分オートエンコーダ](https://scrapbox.io/nishio/変分オートエンコーダ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
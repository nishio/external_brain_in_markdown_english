---
title: "Deployment of GANs in Language Processing"
---

![image](https://gyazo.com/89f4af857610ae486f09b7f2598cd5dd/thumb/1000)
- [Slideshare](https://www.slideshare.net/mamoruk/jsai2018gan4nlp)
    - [[Komachi Mamoru]]
    - [[GAN]] in [[natural language processing]]

I also thought about using GAN for text generation instead of image generation, but I didn't know how to structure it. This slide summarizes it well and I will refer to it.

p.10
Problems in applying GAN to natural language series data
- Problem 1: When dealing with a series, the output of the Generator is a discrete value, making it difficult to train the Discriminator.
1. reinforcement learning (policy gradient), in which the Generator learns as if it were a probabilistic policy
- Approximate the output of the Generator and make it differentiable for learning
- Question 2: What should I use as a Discriminator?
1. CNN/RNN → More complex models ......
2. what constitutes a hostile sample?
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I don't know what you mean by question 1...
- What do you mean by "difficult to learn because of discrete values?"
- Is it because it's a discrete value? Because the length of the output is indefinite?

p.12
SeqGAN: A classic paper on GAN for series data
- Yu et al. SeqGAN: Sequence Generative Adversarial Nets with Policy Gradient (AAAI 2017)
- point
    - - When dealing with a series, it is difficult to learn a discriminator because the output of the generator is a discrete value → Reinforcement learning is used to learn the generator
    - - Discriminator can only evaluate complete series → perform Monte Carlo search
![image](https://gyazo.com/394f2cbcea32a9323ea1a3f673976664/thumb/1000)

- Interpret word sequences as "sequences of actions in reinforcement learning".
- Distribution of the probability of the occurrence of the next word after a word sequence
    - The one called a language model in the field of natural language.
    - In the field of reinforcement learning, they are called probabilistic measures.
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I'm not sure what Monte Carlo search is used for.
    - Looking at the next slide, it doesn't look like it MUST be captured in the framework of reinforcement learning

p.16
- textGAN: Learning GANs for language generation without reinforcement learning
- Zhang et al. [[Feature Matching for Text Generation]] (ICML 2017; textGAN)
- point
    - - Differentiate the Discriminator by [[Soft-argmax]] instead of reinforcement learning
    - - Optimize in latent space rather than discrete words

p.17
p.18
p.19
<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I don't know.

p.20 Better than SeqGAN, apparently.

p.22 MaskGAN
- Can fill in the gaps in the series.
- [[Teacher-Forcing]]

- Mask a portion of the Encoder and have it fill in there.
    - Some kind of [[Dropout]], I guess.

---
This page is auto-translated from [/nishio/言語処理におけるGANの展開](https://scrapbox.io/nishio/言語処理におけるGANの展開) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
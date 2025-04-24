---
title: "Toward Controlled Generation of Text"
---

Sentence Generation Task with Neural Networks
Generator is [[LSTM-RNN]].
The hidden variable z is sampled randomly from the probability distribution output by Encoder
[[VAE]]: [[Variable auto encoder]]
Discriminator takes a sentence as input and makes c
Blue dotted line is the independent constraint proposed in the second half
Red arrows indicate backpropagation made possible by variational approximation
[[GAN]]-like configuration

![image](https://gyazo.com/a10a9ee3a963b880f7470373c273ddb5/thumb/1000)

Learning algorithm alternates between Generator and Discriminator
![image](https://gyazo.com/c2129280c86d21571c7e765c095b00d9/thumb/1000)

> Zhiting Hu, Zichao Yang, Xiaodan Liang, Ruslan Salakhutdinov, Eric P. Xing
> (Submitted on 2 Mar 2017 (v1), last revised 13 Sep 2018 (this version, v4))
> Generic generation and manipulation of text is challenging and has limited success compared to recent deep generative modeling in visual domain. This paper aims at generating plausible natural language sentences, whose attributes are dynamically controlled by learning disentangled latent representations with designated semantics. We propose a new neural generative model which combines variational auto-encoders and holistic attribute discriminators for effective imposition of semantic structures. With differentiable approximation to discrete text samples, explicit constraints on independent attribute controls, and efficient collaborative learning of generator and discriminators, our model learns highly interpretable representations from even only word annotations, and produces realistic sentences with desired attributes. Quantitative evaluation validates the accuracy of sentence and attribute generation.

---
This page is auto-translated from [/nishio/Toward Controlled Generation of Text](https://scrapbox.io/nishio/Toward Controlled Generation of Text) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
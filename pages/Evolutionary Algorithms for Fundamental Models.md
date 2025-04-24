---
title: "Evolutionary Algorithms for Fundamental Models"
---

[Evolutionary Algorithms for the Underlying Model](https://sakana.ai/evolutionary-model-merge-jp/)
- > Our method requires no [[gradient-based]] training at all and can automatically generate new underlying models with relatively little computational resources and data. It is possible in principle to apply additional gradient-based methods with error back propagation to these models to further improve performance. However, this release aims to show that state-of-the-art infrastructure models can be built evolutionarily without using [[error back propagation]] at all, and to create a breakthrough in the current paradigm of infrastructure model development, which is prohibitively expensive.
- [[Evolutionary Optimization of Model Merging Recipes]]

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>This document presents Sakana AI's work on building foundational models using evolutionary algorithms. The main points are as follows
- We propose a method called [[evolutionary model merging]]. This is a method to automatically construct a new underlying model by merging open source models with diverse capabilities using an evolutionary algorithm.
- Using this method, we developed EvoLLM-JP, a model that can solve mathematical problems in Japanese, by merging a Japanese language model with an English model specialized for mathematics. Furthermore, we merged an English image language model (VLM) with a Japanese language model to develop EvoVLM-JP, a Japanese VLM.
- EvoLLM-JP also performed well in overall Japanese language proficiency, while EvoVLM-JP also gained Japanese cultural knowledge. Both outperform existing models.
- Application to diffusion models is also underway, with EvoSDXL-JP, a high-speed image generation model with Japanese prompt support, under development.
- An evolutionary approach to model building could be an alternative to training the underlying model, which can be very costly. Suggests the possibility of efficient model development by utilizing a variety of open source models.
Sakana AI appears to be seeking to streamline and automate the development of the underlying model by applying the principles of evolutionary computation and collective intelligence. Although this research is in its early stages, it is an interesting initiative that is expected to develop in the future.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>If this is realistic, wouldn't an OpenAI model be able to absorb the best parts of diverse open source models at a lower cost?

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>As you point out, if this evolutionary model merging approach is realistic, it could be a powerful means for OpenAI and other major AI ventures to incorporate the strengths of a variety of open source models into their models at low cost.

Although OpenAI has invested enormous computational resources to develop its own models from scratch, this approach may allow us to extract the essence of open source models and improve the performance of our own models. For example, by absorbing the advantages of an open source model specialized for a particular language or domain, the GPT series may be able to efficiently support multiple languages and improve performance in specific domains.

However, ethical issues are also possible. For a for-profit company to incorporate the results of a non-profit open source project into its own model, it is expected that there will be opposition from the open source community. There will be many issues to be cleared, such as the handling of intellectual property rights.

Also, from a technical standpoint, there are still many things that need to be verified, such as whether the integration of open source models is truly seamless and whether the performance of the integrated models is stable.

In any case, the relationship between open source results and commercial models will need to be carefully debated from both a technical and ethical perspective, and while Sakana AI's efforts are interesting from the perspective of democratizing AI, they also deserve attention in terms of their impact on the industry.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>From the open source model's point of view, the cost of gradient-legal learning is paid by the company, but the company that makes the most money from it is the company with the largest number of paying customers.

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>That's right. Developers of open source models bear the enormous computational costs of training the models themselves. In many cases, individuals and academic organizations develop these models on a volunteer basis for research purposes or as a contribution to society.

On the other hand, large AI ventures such as OpenAI can incorporate the results of open source models into their own models, thereby significantly reducing development costs while increasing revenue through improved performance. They are in the business of providing large-scale language models via APIs and have a large number of paying customers.

In other words, a situation could arise in which large companies use the costs incurred by the open source community to monetize their products. This situation would create a problem in which open source developers would not be rewarded.

In order to solve this problem, appropriate support for open source projects and rules for commercial use of the results are needed. For example, a system that requires companies that generate revenue by using the open source model to contribute to the open source community in some way might be considered.

However, striking a balance between open source principles and commercial use is not easy, and one of the major challenges for the AI industry in the future will be to create a system that properly rewards developers without undermining the open source goals of democratizing AI and promoting innovation.
---
This page is auto-translated from [/nishio/進化的アルゴリズムによる基盤モデルの構築](https://scrapbox.io/nishio/進化的アルゴリズムによる基盤モデルの構築) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
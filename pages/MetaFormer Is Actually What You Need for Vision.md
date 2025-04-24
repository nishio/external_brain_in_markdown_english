---
title: "MetaFormer Is Actually What You Need for Vision"
---

[https://arxiv.org/abs/2111.11418](https://arxiv.org/abs/2111.11418)
<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>This paper proposes a general architecture "[[MetaFormer]]" that abstracts the [[attention mechanism]] (token mixer) from the architecture of [[Transformer]]. The main contents are as follows
- Claims that the success of the Transformer and recent MLP models is primarily due to the MetaFormer architecture. The type of token mixer is not important.
- To verify this, we proposed a model called "[[PoolFormer]]" that uses an extremely simple pooling operation for the token mixer and achieves performance comparable to or better than the latest Transformer/MLP models on ImageNet.
- Applied PoolFormer to object detection, instance segmentation, and semantic segmentation, and confirmed its performance over conventional methods such as ResNet.
- We recommend that the future focus should be on improving the MetaFormer architecture itself, and PoolFormer can be used as a baseline for MetaFormer design.
In other words, this paper is ambitious in pointing out that the success factor of Transformer lies not in the attention mechanism but in the remaining architecture, which we call MetaFormer, and suggests the importance of MetaFormer by conducting specific verification experiments.

[[PoolFormer]] is a simple model architecture that replaces the attention mechanism (attention) of Transformer with pooling. The main points are as follows
1. proposed an architecture called MetaFormer that generalizes Transformer; MetaFormer does not specify a token mixer method.
- Pooling is a very simple model compared to attention or Spatial MLP, which learns parameters.
3. PoolFormer achieves the same or better performance as Transformer and MLP-based models in tasks such as ImageNet classification. The number of parameters and computational complexity are much lower.
4. this supports the author's assertion that the overall architecture of MetaFormer is more important to the performance of the model than the method of token mixing.
5. the performance of the PoolFormer suggests that the success of the Transformer is not primarily due to attentions, but comes from the overall structure of the MetaFormer.

In other words, this paper argues that MetaFormer, an abstraction of Transformer, is what is inherently important for high performance in a variety of tasks.

[[Reducing the computational complexity of the attention mechanism]].

---
This page is auto-translated from [/nishio/MetaFormer Is Actually What You Need for Vision](https://scrapbox.io/nishio/MetaFormer Is Actually What You Need for Vision) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
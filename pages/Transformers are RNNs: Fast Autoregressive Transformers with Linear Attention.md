---
title: "Transformers are RNNs: Fast Autoregressive Transformers with Linear Attention"
---

2006.16236 Transformers are RNNs: Fast Autoregressive Transformers with Linear Attention
[https://arxiv.org/abs/2006.16236](https://arxiv.org/abs/2006.16236)
This paper proposes a new method "[[Linear Transformer]]" that significantly reduces the computational complexity and memory usage of transformer models in autoregressive generative tasks. The main contents are as follows.
- The coupling rule of the matrix product is used to compute the self-attention mechanism in linear time. This allows for the computation of self-attention with linear memory and computational complexity with respect to the series length.
- We showed that even autoregressive tasks with causal masks can be computed in linear time and constant memory. This allows the transformer to be treated like an RNN and to perform autoregressive inference at high speed.
- Experiments on image generation and speech recognition showed that the proposed method is able to infer much faster while maintaining performance comparable to conventional transformers. In particular, the proposed method achieved up to 4000 times faster speedup in image generation.
- The linear transformer is formulated as an RNN with a causal mask. This helps in understanding the relationship between transformers and RNNs.

Overall, the linear transformer is a technique that greatly improves the utility of the transformer in autoregressive generative tasks. The linearity of computation and memory usage with respect to series length allows for the handling of long series.

[[Reducing the computational complexity of the attention mechanism]].

---
This page is auto-translated from [/nishio/Transformers are RNNs: Fast Autoregressive Transformers with Linear Attention](https://scrapbox.io/nishio/Transformers are RNNs: Fast Autoregressive Transformers with Linear Attention) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
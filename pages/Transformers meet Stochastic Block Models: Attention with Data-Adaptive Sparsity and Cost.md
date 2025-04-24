---
title: "Transformers meet Stochastic Block Models: Attention with Data-Adaptive Sparsity and Cost"
---

Transformers meet Stochastic Block Models: Attention with Data-Adaptive Sparsity and Cost
[https://papers.nips.cc/paper_files/paper/2022/file/9c93b3cd3bc60c0fe7b0c2d74a2da966-Paper-Conference.pdf#:~:text=URL%3A%20https%3A%2F%2Fpapers.nips.cc%2Fpaper_files%2Fpaper%2F2022%2Ffile%2F9c93b3cd3bc60c0fe7b0c2d74a2da966](https://papers.nips.cc/paper_files/paper/2022/file/9c93b3cd3bc60c0fe7b0c2d74a2da966-Paper-Conference.pdf#:~:text=URL%3A%20https%3A%2F%2Fpapers.nips.cc%2Fpaper_files%2Fpaper%2F2022%2Ffile%2F9c93b3cd3bc60c0fe7b0c2d74a2da966)

This paper proposes a new Transformer model, the SBM-Transformer, which reduces the computational cost of attention mechanisms. The main points are as follows:.
- Each attention head has a stochastic block model (SBM) that adaptively adjusts sparsity based on input data. This allows for flexible cost selection between data-dependent linear to full attention.
- Sampling the graph from the SBM and using its adjacency matrix as an attention mask; Straight-Through estimation allows propagation of the gradient beyond sampling and adjusts the probability of sampled edges based on predictive loss.
- Theoretically, SBM-Transformer was shown to be a universal aproximator for arbitrary inter-sequence functions.
- Experiments on the LRA and GLUE benchmarks show that the proposed method outperforms Transformer and existing efficient methods with full attention.
The model is novel in that it can adapt to the data and adjust its sparsity, allowing for flexibility in changing the computational cost depending on the input. The model showed excellent performance on practical tasks while maintaining its theoretical expressiveness.


[[Reducing the computational complexity of the attention mechanism]].

---
This page is auto-translated from [/nishio/Transformers meet Stochastic Block Models: Attention with Data-Adaptive Sparsity and Cost](https://scrapbox.io/nishio/Transformers meet Stochastic Block Models: Attention with Data-Adaptive Sparsity and Cost) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
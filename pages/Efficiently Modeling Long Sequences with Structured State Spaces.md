---
title: "Efficiently Modeling Long Sequences with Structured State Spaces"
---

[https://arxiv.org/abs/2111.00396](https://arxiv.org/abs/2111.00396)
<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>This paper proposes a new model S4 (Structured State Space) to efficiently model sequences with [[long-term dependencies]]. The main points are as follows
- S4 is based on the [[state space model]](SSM) and combines continuous time, convolution, and recursive representations. This allows long-term dependencies to be captured both theoretically and empirically.
- For computational efficiency, the state matrix A is reparameterized by summing the normal matrix and the low-rank matrix. This allows for diagonalization and faster computation.
- Theoretically works with O(N+L) amount of computation and space, where N is the state size and L is the sequence length.
- Significantly outperforms conventional methods in various benchmarks. Can be applied universally to a wide range of tasks, including image classification, language modeling, and time series prediction.
- Especially in Long Range Arena, which consists of ultra-long sequences of 16,384 steps, the average accuracy is as high as 86%.
- Achieves high performance approaching that of Transformer and 60 times faster generation, even for large-scale generation tasks.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>What is a state space model?

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>State Space Model (SSM) is a probabilistic framework for modeling time series data. It has been used mainly in the fields of control theory and time series analysis, but in recent years it has also attracted attention in machine learning, especially in deep learning.

SSM considers two types of variables: observable variables (observations) and hidden variables (latent variables or hidden states) that cannot be directly observed. Hidden variables represent the internal state of the system, and their temporal transitions model the creation process of observed variables.
(Formula omitted)
The advantages of SSM include the ability to explicitly model the dynamics of the system, the abundance of statistical methods for state and parameter estimation, and its affinity with control theory.

In recent deep learning, there have been many attempts to use SSM as a generalization of RNNs and to combine SSM with deep neural networks. S4 in this paper is also in this vein, aiming at modeling long-term dependence and improving computational efficiency by using the SSM framework.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>What improvement is S4?

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>S4 (Structured State Space Sequence model) improves on the existing model in the following ways

- Modeling of long-range dependencies: S4 effectively captures long-term dependencies in long sequences by using a state-space modeling framework. In particular, the state matrix A is designed based on the theory of HiPPO (High-order Polynomial Projection Operator) to achieve long-term memory.
- Improved computational efficiency: Conventional state-space models are computationally expensive and difficult to handle long sequences; S4 solves this problem by representing the state matrix A as the sum of a normal matrix and a low-rank matrix (Normal Plus Low-Rank; NPLR) and introducing an efficient algorithm S4 introduces an efficient computational algorithm. This achieves a computational complexity of O(L+N) for a sequence length L and state dimension N.
- Potential as an alternative to Transformer: S4 has shown its potential as a new sequence model that can replace Transformer as well as RNNs and CNNs. combining LayerNorm, Residual connection, etc., S4 achieves performance comparable to or even better than Transformer for various tasks such as image classification, language S4 has achieved performance comparable to or even better than Transformer in a variety of tasks, including image classification, language modeling, and time series prediction.
- Balancing Theory and Practice: S4 is based on mathematical principles such as HiPPO, yet its effectiveness has been demonstrated through extensive experimentation. Theoretical support makes the behavior of the model easy to interpret and provides guidance for further improvements.

Overall, S4 is a groundbreaking study that uses a state-space modeling framework to both model long-term dependencies and improve computational efficiency, and shows the potential for a new sequence model to replace Transformer. This balanced approach between theory and practice will have a significant impact on future sequence modeling research.


---
This page is auto-translated from [/nishio/Efficiently Modeling Long Sequences with Structured State Spaces](https://scrapbox.io/nishio/Efficiently Modeling Long Sequences with Structured State Spaces) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
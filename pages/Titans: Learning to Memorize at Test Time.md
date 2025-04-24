---
title: "Titans: Learning to Memorize at Test Time"
---

[https://arxiv.org/abs/2501.00663](https://arxiv.org/abs/2501.00663)

<img src='https://scrapbox.io/api/pages/nishio-en/o1 Pro/icon' alt='o1 Pro.icon' height="19.5"/>The following is a brief summary of the paper "Titans: Learning to Memorize at Test Time" in Japanese.

Background and Objectives
- Conventional [[Transformer]] has the advantage of modeling short-term dependencies using [[attention]], but its computational cost increases to the square of the context length, making it difficult to apply to long contexts. Also, RNNs (recurrent neural networks) want to handle long-term dependencies, but they pack information into hidden states of fixed dimension, making scalability and high accuracy an issue.
- Inspired by the two types of human memory models, "short-term memory (temporarily retained)" and "long-term memory (permanently stored)," we propose a new neural long-term memory module that can learn and reason efficiently and accurately even with long input sequences. This module will be combined with short-term memory (attention) such as Transformer to create a new family of "Titans" to realize a highly versatile long-text processing model.

Core Methodology: Neural Long-Term Memory Module
- Basic Idea
    - The module adopts a "meta-learning" structure that updates parameters even during testing, and accumulates information during the sequence as its own parameters (weights) "on the fly.
- Surprise-based updates
    - The weights are updated based on the amount of gradient (i.e., the degree of surprise) in response to the input, taking into account the nature of human memory that "inputs that significantly betray predictions are more likely to be remembered. In addition, by introducing a momentum term for the gradient, we can deal with the case where "a surprise at a certain point in time lasts a little longer" and retain important information for a longer period of time.
- forgetting mechanism
    - By introducing a "weight decay" gate in conjunction with the learning rate for weights, information that is no longer needed is sequentially eliminated and memory capacity is automatically controlled.
- Deep memory structure
    - Instead of mere linear transformations, deeper structures such as multi-layer MLPs can be employed to represent more complex long-term patterns.

Titans Architecture
- Titans is a new family of series models that combines three elements: short-term + long-term + permanence (task knowledge). The proposal presents the following three methods for incorporating the long-term memory module

- MAC (Memory as a Context)
    - The "old information" returned by the long-term memory module is processed together as the input context for the attention.
    - Attention stores "past information needed now" in memory while discarding it.
- MAG (Memory as Gating)
    - Two systems, short-window attention (short-term memory) and long-term memory, are run in parallel and finally integrated by gates (nonlinear coupling).
- MAL (Memory as a Layer)
    - Insert long-term memory as one layer of the network, and perform normal (or sliding window type) attention after passing through it.

In all schemes, the structure is such that the attention captures "locally precise dependencies" and the long-term memory module plays the role of "dynamically storing and referencing the entire past.

experimental results
- Linguistic Modeling and Reasoning Tasks
    - It outperforms Transformer systems and state-of-the-art linear recursive models (Mamba, DeltaNet, etc.) on long language tasks such as Wiki and LAMBADA, physical common sense and machine reading tasks.
- [[Needle in a Haystack]], BABILong, etc.
    - The system is strong in the task of extracting necessary information from a huge amount of dummy contexts and can scale to contexts up to millions of tokens in size.
    - It has also shown effectiveness in genome sequence modeling and time series prediction, and can be applied to a variety of series data other than natural language.

summary
- The proposed method combines "long-term memory (gradient-based) + short-term memory (attention) + persistent task knowledge," and its main feature is a structure that continues to learn long-term memory even during testing.
- Forgetting gates + surprise indicators with momentum effectively compress and retain information over long periods of time and delete unnecessary information.
- Experiments showed that the model outperformed the Transformer system and existing recurrent systems on a variety of benchmarks, and demonstrated its high versatility as a model that can be applied to very long contexts.

These are the main points of the paper: the Titan architecture is a new approach to incorporating long-term learning during testing.
---
This page is auto-translated from [/nishio/Titans: Learning to Memorize at Test Time](https://scrapbox.io/nishio/Titans: Learning to Memorize at Test Time) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Hard attention mechanism"
---

attention mechanism
$Attention(query, Key, Value) = Normalize(Func(query, Key)) \cdot Value$
The Normalize part of the "Normalize" is not Softmax, but "a function that samples from the Softmax result and returns a one-hot representation".

- There is a very big disadvantage of not being able to differentiate, but what is the advantage?

- Can be applied when the space of Values is not a vector space
    - Values space must be scalar doubled and additive for soft attention
    - For example, the space of symbols is not a vector space.
    - Function that samples from the Softmax results and returns a one-hot representation."
        - For one-hot expression x $x\cdot V = V[x]$
    - I'm sampling from a vector of |V| in the NN of a system that outputs words, which can be interpreted as a hard attention mechanism.
        - The word is Value and the one-hot expression of the word is Key
        - If the word is a distributed representation, it is much easier to understand. Take the inner product, softmax, and sample from there = hard caution.

[https://jhui.github.io/2017/03/15/Soft-and-hard-attention/](https://jhui.github.io/2017/03/15/Soft-and-hard-attention/)
> Hard attention replaces a deterministic method with a stochastic sampling model. To calculate the gradient descent correctly in the backpropagation, we perform samplings and average our results using the Monte Carlo method. Monte Carlo performs end-to-end episodes to compute an average for all sampling results. The accuracy is subject to how many samplings are performed and how well it is sampled. On the other hand, soft attention follows the regular and easier backpropagation method to compute the gradient. However, the accuracy is subject to the assumption that the weighted average is a good representation for the area of attention. Both have their shortcomings. Currently, soft attention is more popular.

---
This page is auto-translated from [/nishio/ハード注意機構](https://scrapbox.io/nishio/ハード注意機構) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
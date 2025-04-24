---
title: "attention"
---

<img src='https://scrapbox.io/api/pages/nishio-en/GPT-4/icon' alt='GPT-4.icon' height="19.5"/>Attention is the psychological process by which we focus [[focal point]] on certain events or information and [[ignore]] others. In general, our [[awareness]] is [[limited resources]] and we cannot pay attention to all information at the same time. Therefore, our brain deals with [[information overload]] situations by focusing on information that is deemed [[important]] in the moment.

## machine learning context:
- [[attention (heed)]] ,  [[attention mechanism]]
    - [[addition caution]]
    - [[internal volume caution]]
    - [[Source Target Attention]]
    - [[self-caution]]

- Note A is defined with query q, key k, and value v as follows
- $A(Q, K, V) = \mathrm{softmax}(QK^T)V$
- Additive and Intra-product Caution
    - Theoretically, the complexity is about the same, but the inner product attention can be computed with matrix products, so it is faster in practical use.
    - The claim that scaling with the dimension dk of the key gives better performance
- $A(Q, K, V) = \mathrm{softmax}({QK^T \over \sqrt{d_k}})V$

---
This page is auto-translated from [/nishio/アテンション](https://scrapbox.io/nishio/アテンション) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
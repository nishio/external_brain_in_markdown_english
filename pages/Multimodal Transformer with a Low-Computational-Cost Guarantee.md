---
title: "Multimodal Transformer with a Low-Computational-Cost Guarantee"
---

[https://ar5iv.labs.arxiv.org/html/2402.15096v1](https://ar5iv.labs.arxiv.org/html/2402.15096v1)
In this paper, we propose a new attention mechanism, the Low-Cost Multimodal Transformer (LoCoMT), to reduce the computational cost of the Multimodal Transformer.
The main points are as follows
- By assigning a different multimodal attention pattern to each attention head, LoCoMT guarantees flexible control of multimodal signals while theoretically reducing computational cost compared to existing multimodal Transformers.
- Experiments on two multimodal datasets, Audioset and MedVidCL, demonstrate that LoCoMT not only reduces GFLOPs but also performs as well or better than established models.
- The tradeoff between performance and efficiency in various LoCoMT configurations was investigated, and it was shown that nearly half of the GFLOPs could be saved with little loss of performance.
- We explored the impact of assigning different attention patterns to different tiers and found that self-attention helps improve performance in the low-level tier, while random attention patterns work well in the high-level tier.

In summary, we conclude that LoCoMT is a promising approach for efficient multimodal fusion that can significantly reduce computational costs while maintaining high performance.

[[Reducing the computational complexity of the attention mechanism]].

---
This page is auto-translated from [/nishio/Multimodal Transformer with a Low-Computational-Cost Guarantee](https://scrapbox.io/nishio/Multimodal Transformer with a Low-Computational-Cost Guarantee) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
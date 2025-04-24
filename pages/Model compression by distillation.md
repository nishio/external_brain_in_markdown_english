---
title: "Model compression by distillation"
---

- Cannot be deployed with current hardware constraints
- However, hardware performance will continue to increase, so I suspect that in the near future, a simple [[ensemble]] will do the job.

- Learning student models with output of teacher models
    - Cases where Softmax output is used as-is instead of one-hot
        - [[soft target loss]]
        - Equivalent to [Label smoothing

[1503.02531 Distilling the Knowledge in a Neural Network](https://arxiv.org/abs/1503.02531)


- [[Paying More Attention to Attention: Improving the Performance of Convolutional Neural Networks via Attention Transfer]]
    - Student model learns [[attention (heed)]] of teacher model

- [[Born Again Neural Networks]]
    - Student performs better when the same model is used by teacher and student

- [[Deep Mutual Learning]]
    - Students teach each other.

---
This page is auto-translated from [/nishio/蒸留によるモデル圧縮](https://scrapbox.io/nishio/蒸留によるモデル圧縮) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
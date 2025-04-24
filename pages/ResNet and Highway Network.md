---
title: "ResNet and Highway Network"
---

![image](https://gyazo.com/3ece755849cf9ae710151121e2a7c36a/thumb/1000)

Highway Network
- [https://arxiv.org/pdf/1505.00387.pdf](https://arxiv.org/pdf/1505.00387.pdf)
- There are non-linear transformations F, G, and
- $z = F(y) \otimes G(y) + y \otimes (1 - G(y))$
    - G is made to return a value in the range 0 to 1, which is a mixing factor between passing y through bare (0) or using only F(y) (1)

Residual Block
- [[ResNet]] configuration block
- In comparison to Highway Network.
- $z = F(y) + y$
- Mixing ratio fixed at 1:1
    - Is "mixing" a bad word because it's misleading as if it's 0.5 and 0.5?
    - As the name "Residual" implies, F learns z-y: $F(y) = z - y$.

---
This page is auto-translated from [/nishio/ResNetとHighway Network](https://scrapbox.io/nishio/ResNetとHighway Network) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Half of the queue"
---

When matrix A is symmetric
$\sum_{i=1}^{N-1} \sum_{j=i+1}^N A_{ij} = \left(\sum_{ij} A_{ij} - \sum_i A_{ii}\right) / 2$
- Specific examples [[ABC177C]].
    - $A_{ij} = A_iA_j$ when $\sum_{i=1}^{N-1} \sum_{j=i+1}^N A_iA_j = \left(\sum_{ij} A_iA_j - \sum_i A_i^2\right) / 2$
        - Note that $\sum_{ij} A_iA_j = \left(\sum A_i\right)^2$

Especially when the diagonal component is 0
- $\sum_{i=1}^{N-1} \sum_{j=i+1}^N A_{ij} = \left(\sum_{ij} A_{ij}\right) / 2$
- Specific examples [[ABC194]]C
    - $A_{ij} = (A_i - A_j)^2$ when $\sum_{i=1}^{N-1} \sum_{j=i+1}^N A_{ij} = \left(\sum_{ij} (A_i - A_j)^2 \right) / 2$
- [[ABC147D]]
    - $A_{ij} = A_i \oplus A_j$

---
This page is auto-translated from [/nishio/行列の半分](https://scrapbox.io/nishio/行列の半分) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
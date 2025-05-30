---
title: "end-to-end memory networks"
---

from [[Memory Network]]
end-to-end memory networks
Sukhbaatar, S., Weston, J., & Fergus, R. (2015). End-to-end memory networks. In Advances in neural information processing systems (pp. 2440-2448).
The input sentence $x_i$ is embedded with the sum of the embedded representations of each word
$m_i = \sum_j Ax_{ij}$
The question text q is embedded as well
$u = \sum_j Bq_j$
The importance p of each of the N stored information to u is the soft max of the inner product
$p_i = \mathrm{softmax}(u \cdot m_i)$
$o= p \cdot \sum_j Cx_{ij}$
In short [[soft attention mechanism]].
$\hat{a} = \mathrm{softmax} (W(o+u))$
Is such a design acceptable in many ways? However, the constraint that the entire system must be differentiable in order to optimize end-to-end is severe.
![image](https://gyazo.com/87e61c10f3997c3f3b7fe412b2b08aea/thumb/1000)


---
This page is auto-translated from [/nishio/end-to-end memory networks](https://scrapbox.io/nishio/end-to-end memory networks) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
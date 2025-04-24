---
title: "storage network"
---

- [[Natural Language Processing with Deep Learning]]  p.99
[arXiv: Memory Networks](https://arxiv.org/abs/1410.3916)
- [[Strongly supervised memory network]]

Memory addition: $m_N \leftarrow x$
Memory retrieval:.
$o_1 = \mathrm{argmax}_i S_O(x, m_i)$
$o_2 = \mathrm{argmax}_i S_O((x, m_{o_1}, m_i)$
- <img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Isn't $o1\neq o2$ guaranteed in this form?
$r = \mathrm{argmax}_{w\in \mathcal{V}} S_R((x, m_{o_1}, m_{o_2}), w)$

SO and SR, respectively.
$s(x,y) = \Phi(X)^T \; U^T \; U \; \Phi(y)$
$\Phi$ is embedded in the D dimension
The real problem is whether or not we can prepare the teacher data necessary for the training of SO and SR.

So end-to-end memory network
[[end-to-end memory networks]]
---
This page is auto-translated from [/nishio/記憶ネットワーク](https://scrapbox.io/nishio/記憶ネットワーク). If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
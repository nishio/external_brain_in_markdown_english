---
title: "Summary generation using attention mechanism"
---

- [[summary generation]] # summary using [attention mechanism
- [[Natural Language Processing with Deep Learning]]  p.136
[A Neural Attention Model for Abstractive Sentence Summarization](https://arxiv.org/abs/1509.00685)

- [[attention mechanism]]
Using a fixed-length C forward propagation network instead of an RNN.
- Later studies have shown RNNs to be more accurate, so this is just a historical story of how it was when it was first created.
Using context length C $Y_< = Y_{[j-C,\,j-1]}$
The conditional probability of a summary statement output Y for an input statement X can be written as follows.
$P(Y|X) = \prod_j P(y_i | X, Y_<)$
$P(y_i | X, Y_<) = \mathrm{softmax}(\tilde{o_j})\cdot y_j$
$\tilde{o_j} = \mathrm{nnlm}(Y_<) + \mathrm{enc}(X, Y_<)$

![image](https://gyazo.com/f0fdaffe41b8b0cf70ccca0b8595c7ac/thumb/1000)
![image](https://gyazo.com/6f0f768522bc299f78caf8ea07e6274e/thumb/1000)

---
This page is auto-translated from [/nishio/注意機構を用いた要約生成](https://scrapbox.io/nishio/注意機構を用いた要約生成) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
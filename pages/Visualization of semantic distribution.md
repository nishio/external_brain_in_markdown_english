---
title: "Visualization of semantic distribution"
---


<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>I want to overlay a Japanese embedding vector and an English embedding vector to visualize that a certain Japanese word does not have an English word that corresponds very well
<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>In order to superimpose Japanese and English embedding vectors and visualize the situation where an English word corresponding to a certain Japanese word is not found well, a method is needed to first prepare Japanese and English word embedding vectors and map them into the same space. Typically, an approach that uses a pre-trained word embedding model (e.g., Word2Vec, GloVe, FastText, etc.) and then aligns the vector spaces of the two languages through linear transformation (e.g., solving Orthogonal Procrustes problems) is employed.

---
Orthogonal Procrustes issue, I didn't know about it, but it is appropriate.
> Procrustes analysis (also called procrustes analysis) is a process of superposition of two well-corresponding point groups under translational, rotational, and uniform scaling transformations such that the squared error between the point groups is minimized. This article deals specifically with Orthogonal Procrustes analysis in the case where the rotation matrix is an orthogonal matrix.
[Procrustes Analysis - Hijiyama Diary](https://gv.hateblo.jp/entry/2017/10/24/222528)

relevance
- [[Nattoku in Vector space]]


---
This page is auto-translated from [/nishio/意味分布の可視化](https://scrapbox.io/nishio/意味分布の可視化) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
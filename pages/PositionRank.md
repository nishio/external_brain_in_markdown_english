---
title: "PositionRank"
---

PositionRank: An Unsupervised Approach to [[Keyphrase Extraction]] from Scholarly Documents
    - [[keyphrase extraction]]  2017
- [http://people.cs.ksu.edu/~ccaragea/papers/acl17.pdf](http://people.cs.ksu.edu/~ccaragea/papers/acl17.pdf)

Calculate [[PageRank]] by graphing word adjacencies
While the usual PageRank method applies equal probability bias, this method weights words by the inverse of their position of occurrence, rather than by equal probability.
This is an improvement over the traditional PageRank-based method.

After first discarding all but nouns and adjectives, a sequence of up to three words of the form `(objective)*(noun)+` is extracted as a key phrase.

It is claimed that Window size has little effect, but if it is limited to the above form, the chance that being Window size > 1 will work is very limited.

I am not quite sure what the significance of using PageRank for keyword extraction is. In fact, simple [[TextRank]] is losing out to [[TF-IDF]].

Someone was implementing it.
[Key phrase extraction from arXiv papers with PositionRank - Qiita](https://qiita.com/ymym3412/items/bc3d90e9e1b51959649a)

---
This page is auto-translated from [/nishio/PositionRank](https://scrapbox.io/nishio/PositionRank) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
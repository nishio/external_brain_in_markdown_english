---
title: "Similarity of concepts is not distance."
---

- [[Natural Language Processing with word2vec]], p.64, where I wrote
> Apples and tomatoes are similar. Both are red. Apples and green apples are similar. Both are apples. However, green apples and tomatoes are not so similar.

This phenomenon does not satisfy the [[trigonometric inequality]] requirement of [[distance]].

How to solve this problem
- Instead of treating the distance [[Vector similarity]] between vectors as it is, the distance after collapsing the vectors on various axes is used as the similarity #Collapse axes
![image](https://gyazo.com/6f605fd9a0082f691b3b93c575ccd69e/thumb/1000)

- To [[thwart]] a vector in an axial direction means to [[ignore]] the difference in that axial direction.
    - [[Dimensionality reduction is an abstraction]] #abstraction #ignore features #ignore differences
- I doubt that one axis of the vector created by the current [[word2vec]] represents a convenient attribute like "color difference".
    - word2vec creates vectors based solely on the information of what words appear around a word, so it is not possible to create vectors based on the information of what words appear around a word.
- I think something similar is going on in the human brain.
- One of the techniques used in [[Deep Learning]] is [Dropout
    - A method of randomly selecting a [[neuron]] and stopping its activity to allow it to learn
    - Doing this increases [generalization performance
    - Stop the activity of randomly selected neurons
        - = set the value represented by that neuron to 0
        - = Crush in the direction of a randomly selected axis

- [[degree of similarity]] in [[concept]] is not [distance
- [[Word Meaning]]
- [[semantic similarity]]

- [[People who leap from one story to the next = vector search engines?]]
    - Is [[suggestion]] a vector search? I think not.
    - Random [[dimensionality reduction and then similarity search]].
---
This page is auto-translated from [/nishio/概念の類似度は距離ではない](https://scrapbox.io/nishio/概念の類似度は距離ではない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
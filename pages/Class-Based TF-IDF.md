---
title: "Class-Based TF-IDF"
---

from [[BERTopic: Neural topic modeling with a class-based TF-IDF]]
Class-Based TF-IDF
Class-based TF-IDF is a new topic representation method proposed in BERTopic.

Normal TF-IDF calculates the importance of a word in each document. On the other hand, class-based TF-IDF groups documents by topic and considers them as one pseudo document, and calculates the importance of words in that document class.

Specifically, it is calculated as follows

Wt,c = tft,c · log(1 + A/tft)

- tft,c : frequency of occurrence of the word t in documents contained in topic c
- A : Average frequency of words in the corpus
- tft : Frequency of occurrence of word t in the whole corpus

While regular TF-IDF treats each document independently, class-based TF-IDF is unique in that it groups documents by topic. This allows for a more direct calculation of the importance of words that characterize a topic.

BERTopic states that using this class-based TF-IDF for generating topic representations has yielded better results than traditional cluster-centric-based topic representations. It can be said that this method contributes to improving the interpretability of topics.


---
This page is auto-translated from [/nishio/クラスベースTF-IDF](https://scrapbox.io/nishio/クラスベースTF-IDF) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
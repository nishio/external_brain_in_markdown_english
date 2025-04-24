---
title: "BERTopic: Neural topic modeling with a class-based TF-IDF"
---

[2203.05794 BERTopic: Neural topic modeling with a class-based TF-IDF procedure](https://arxiv.org/abs/2203.05794)
[[BERTopic]]: Neural [[topic model]]ing with a [[class-based TF-IDF]] (2022)

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Summary: /What is a class-based TF-IDF? /What are the advantages over LDA and other methods? /What is HDBSCAN used for? What is /UMAP used for? By what metric do you claim this method is superior? /What is CTM? /The above exchange should be a summarized exchange to be saved in my notebook, while preserving my question text.

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>BERTopic is a new topic model using pre-trained language models and class-based TF-IDF. Compared to traditional LDA and other methods, it has the following advantages
- Enables topic modeling that takes into account the context of words by leveraging language models
- Separate document clustering and topic representation generation for flexible architecture
- Easily applied to dynamic topic modeling
- Stable performance in different language models

In BERTopic, documents are first embedded into high-dimensional vectors in a language model. Next, it extracts topics by dimensionality reduction using UMAP and clustering using HDBSCAN. Finally, a class-based TF-IDF is used to generate topic representations.

- [[Class-Based TF-IDF]] groups documents by topic and calculates the importance of words within each group. This allows more direct extraction of words that characterize a topic.

[[UMAP]] is a nonlinear dimensionality reduction method that preserves the local and global structure of high-dimensional data while efficiently embedding it in a low-dimensional space. [[HDBSCAN]] is a density-based clustering method that provides noise-robust clustering without specifying the number of clusters.

BERTopic shows excellent performance on the topic consistency and topic diversity measures, and has an advantage in computational efficiency compared to other state-of-the-art methods such as CTM. However, challenges remain, such as the inability to directly model that a single document has multiple topics.

[[CTM]] is a state-of-the-art topic model that, like BERTopic, leverages language models. It takes a [[VAE]]-based approach and learns topics end-to-end by integrating contextual information and frequency of occurrence of words. It shows excellent results in topic quality, but suffers from high computational cost.

- [[Class-Based TF-IDF]]
---
The evaluation indicators are oversimplified.

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>
The superiority of BERTopic is evaluated and claimed mainly by the following two indicators

1. topic coherence
Topic coherence is a measure of the degree to which the words comprising a topic are semantically coherent. Specifically, it is calculated based on semantic similarity and co-occurrence probability between words within a topic.

The paper uses a measure of topic consistency called Normalized Pointwise Mutual Information (NPMI), which is calculated from the co-occurrence probability of word pairs within a topic and the occurrence probability of each word.

Experimental results show that BERTopic achieves higher NPMI scores than conventional methods such as LDA and NMF. This suggests that BERTopic can generate semantically coherent topics.

2. topic diversity
Topic diversity is a measure of the degree of overlap between generated topics. The less overlap of words between topics, the higher the topic diversity is considered.

The paper defines topic diversity as the percentage of unique words in all topics; closer to 0 indicates more topic overlap and closer to 1 indicates more topic diversity.

Experimental results report that BERTopic achieves relatively high topic diversity, but not as high as CTM. However, BERTopic has shown greater performance stability with language model selection than CTM.

In addition to these metrics, the paper discusses the computational efficiency of BERTopic, which has been shown to be significantly faster than CTM and can process large data sets in realistic time.

As described above, BERTopic shows superior performance compared to conventional topic models in terms of topic consistency, topic diversity, and computational efficiency. It should be noted, however, that as the authors acknowledge, these automatic evaluation metrics are only approximations, and subjective evaluation by actual users is also important.


---
[BERTopic](https://maartengr.github.io/BERTopic/index.html#modularity)
[[CountVectorizer]]

[[Clustering Topics]]

---
This page is auto-translated from [/nishio/BERTopic: Neural topic modeling with a class-based TF-IDF](https://scrapbox.io/nishio/BERTopic: Neural topic modeling with a class-based TF-IDF) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
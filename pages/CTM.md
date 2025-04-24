---
title: "CTM"
---

from [[BERTopic: Neural topic modeling with a class-based TF-IDF]]

<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>
CTM (Contextualized Topic Model), like BERTopic, is one of the latest topic models to leverage pre-trained language models; CTM was proposed in 2020, shortly before BERTopic was announced.

The main features of the CTM are as follows

1. use of contextual embedding in BERT
CTM uses a pre-trained language model, such as BERT, to capture the contextual information of words. Specifically, each word is input into BERT and the output is averaged to obtain a context-aware word embedding.

2. VAE-based topic model
CTM is a topic model based on variational autoencoder (VAE); VAE is a type of latent variable model that can model the process of data generation; in CTM, topic and topic-word distributions are treated as latent variables and estimated using VAE.

3. integration of word context information and word frequency
CTM uses both contextual information (BERT embedding) and frequency of occurrence of words to learn topics. This makes it easier to assign contextually related words to the same topic.

4. end-to-end learning
CTM simultaneously estimates the topic distribution and the topic-word distribution. This ensures that the topic distribution and topic-word distribution are optimized in a mutually influential manner.

CTM outperforms traditional topic models such as LDA and ProdLDA on several benchmark data sets. In particular, it achieves superior results for both topic consistency and topic diversity.

However, CTM is computationally more expensive than BERTopic and is difficult to apply to large data sets. Also, unlike clustering-based approaches such as BERTopic, the number of topics must be specified in advance.

As described above, CTM, along with BERTopic, is the newest neuraltopic model and has in common the use of language models to improve topic quality, but the details of the approach differ. It is important to understand the advantages and disadvantages of each, and then choose the appropriate model for the task.

---
This page is auto-translated from [/nishio/CTM](https://scrapbox.io/nishio/CTM) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
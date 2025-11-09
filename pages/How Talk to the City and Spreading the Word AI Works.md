---
title: "How Talk to the City and Spreading the Word AI Works"
---

How [[Talk to the City]] and [[public information AI]] work

Cut out from a certain manuscript because it is useful and share it

Here's a brief explanation of how Talk to the City and the broadband AI work.

First, LLM extracts fine-grained expressions from natural language data such as people's utterances.
- The data can be any list of strings.
- In the past, we have used APIs to extract items containing specific keywords from social networking sites such as X (Twitter), collected opinions on a subject using Google Form, collected reviews written in a specific geographic area on Google Maps, collected comments on games on Steam, and so on. and other activities have been carried out.

What is extracted as a "fine-grained representation" is controlled by prompts to the LLM and can be changed depending on the use case.
- For example, "opinions" can be extracted.
- Other examples include extracting "questions," "criticisms," and "problem awareness.
- Some user submissions may contain more than one opinion, while others may contain no opinion.
- The processing of the two extraction phases creates a granular set of objects for analysis from a wide variety of user submissions.

Prior to Talk to the City, this fine-grained representation extracted was "keywords" or "topics.
- So it was a word or a phrase of a few words.
- Talk to the City extracts short sentences.
- This allows for better retention of meaning.

In the next step after the extraction step, the short sentences are embedded in a high-dimensional space of several thousand dimensions using LLM.
- This technology, which began with word2vec in 2013, has made great strides in the 2020s with the advent of BERT and GPT.
- This embedding vector is designed so that semantically similar short sentences are placed close together.
- This embedding vector allows us to treat semantically similar short sentences as mathematically close.
- This made it possible and useful to extract short sentences rather than keywords as the fine-grained expression to be extracted in the previous extraction step.

There are many variations after this step.
- For example, a vector distribution of thousands of dimensions can be dimensionally reduced to two dimensions and visualized as a scatterplot using UMAP, a time reduction method invented in 2018.
- Clustering can be applied to vectors of higher or lower dimensions to create groups of "opinions of similar meaning.
- The LLM can read and generate commentary on what opinions exist in the groups created by the clustering.

A unique feature of the wide hearing AI is the use of hierarchical clustering in this clustering portion.
- For example, 8,000 data items can be divided into 20 rough groups for observation, and then further divided into 20 detailed groups for in-depth observation of items of interest.
- Technically, the clustering is done in two steps: first, 400 clusters are created using the k-means method, and then hierarchical clustering is applied to each cluster to agglomerate it down to 20 cases.

As explained in my book "The Intellectual Production Techniques of Engineers," this style of first taking a broad overview and then digging deeper into areas of interest is extremely effective in intellectual production.
- Traditionally, such a hierarchical table of contents had to be created manually by humans.
- It is very difficult for a human being to organize the data with so many people saying so many different things.
- Technologies such as Wide Hearing AI make it possible for AI to automatically generate a hierarchical table of contents to support human intellectual production.

Another feature of the Wide Hearing AI is the ability to focus on "[[Strong Opinion Groups]].
- This is a function that uses the density of points in a vector space to select clusters of interest.
- For example, when 8,000 pieces of data are divided into 400 clusters, one of the 400 clusters will contain, on average, 20 pieces of data, or 0.25% of the total data.
- This has tended to be truncated as a minority opinion, less than 1%, until now.
- However, if these 20 data were, for example, similar problematics extracted from different people's differently requested texts, this could lead to important findings.
- In other words, this is a discovery aid for "[[unforeseen connection]]".
- Of course, repeated postings by the same person or organized postings by people in close proximity will also increase the density, so this measure alone cannot be used to determine importance.
- In the future, scoring will evolve to take into account the diversity of contributors and other factors.

---
This page is auto-translated from [/nishio/Talk to the Cityと広聴AIの仕組み](https://scrapbox.io/nishio/Talk to the Cityと広聴AIの仕組み) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
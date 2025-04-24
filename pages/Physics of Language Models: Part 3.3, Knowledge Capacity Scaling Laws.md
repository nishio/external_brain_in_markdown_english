---
title: "Physics of Language Models: Part 3.3, Knowledge Capacity Scaling Laws"
---

[2404.05405 Physics of Language Models: Part 3.3, Knowledge Capacity Scaling Laws](https://arxiv.org/abs/2404.05405)

Very interesting story.
The MLP layer stores the "newly learned" inefficiently about 100 times, and then changes to the Attention layer storing it in an efficient way about 1000 times after that.

> [hillbig](https://twitter.com/hillbig/status/1779640139263901698) LLM can store 2 bits of information per parameter in a form that can be used for various subsequent tasks. I think this is the most important result since the power law paper including other results. Artificially designed triads (name/attribute/value) and tested on various scales and architectures; even the 7B model can remember wikipedia and all textbook information. [https://arxiv.org/abs/2404.05405](https://arxiv.org/abs/2404.05405)
>
>  Interesting results in all of the following
>
>  This paper treats knowledge as a simplified set of triads.
>  wikipedia has 4.5 billion words, and about 100,000 English textbooks, excluding duplicates, can cover about 1.6 billion words, assuming each book has 160,000 words. If we assume that each book contains 160,000 words, the total number of words is about 1.6 billion words, which is 20 billion words, and the knowledge contained in these words is considered to be less than 14 billion bits.
>
>  This knowledge density cannot be achieved without 1000 exposures per each piece of knowledge during learning (1000-exposure), and we know from the paper before that it is better to have a different representation each time (exposing the same sentence many times leads to memorization of the sentence). In our experiments, we artificially generated different representations.
>
>  Also, if it is only touched 100 times, the memorizable capacity drops to 1 bit/parameter. Thus, rare knowledge that is not often encountered during learning is inefficiently memorized.
>
>  2 bits/parameter is universal and is achieved in the same way even when the MLP block, which was thought to be a key component of memory, is completely excluded. This indicates that the self-attention mechanism also plays a role in memory, unlike previously assumed.
>  On the other hand, in the case of 100-exposure, memory efficiency deteriorates sharply without the MLP layer; the MLP layer can remember less knowledge with fewer exposures, but neither the MLP nor the self-attention mechanism changes in terms of storage capacity.
>
>  Although not tested in detail, it appears that knowledge is not stored in a single location, but is scattered throughout the NN, including in the last layer of the experiment, which was excluded.
>
>  Gated MLP used in many modern LLMs worsens memory capacity and destabilizes learning. Other activation and tokenization differences are not related to memory capacity (even GPT-2 is as good as the latest architectures and better than models using Gated MLP as long as rotary embedding is used). The results have implications for future NN design.
>
>  Quantization has no effect on storage capacity up to int8, and storage capacity deteriorates drastically from int4. Put another way, if 2 bits of information are stored in NN in 8 bits (int8), the rest can be used at will. If NN is considered as an index for free use in subsequent tasks, the limit of indexing overhead is 4 times. It may be more possible if quantization is taken into account from the learning process.
>
>  If 32 experts are used in MoE, only 8.8% of the parameters are used during inference, but the capacity is 1.3 times worse and 100-exposure is only 1.5 times worse.
>
>  In addition, if the training data contains poor quality data, it has a significant impact on storage capacity, with storage capacity deteriorating by a factor of 20 in the case of 100-exposure.
>
>  The ingenious solution to this is simple: just tell the LLM that the data is of good quality with a special token in front of the quality data (wikipedia, textbooks, etc.), and the storage capacity will be improved almost to the optimum.
>
>  == Thoughts on the following ==
>  In the case of real world data, the number of times the same knowledge is exposed is like a power law, the famous ones appear more than 100~1000 times (like Tokyo for the capital of Japan), but the knowledge at the end of the distribution that most only know a part of is much less than 100 times, I think mostly 10 times or 1 time. I think that the knowledge of the end of the distribution is much less than 100 times. In the current LLM study, it is 1~2 epochs.
>
>  In the future, we need to devise a way to memorize NN with fewer exposures, or to concentrate and regenerate the knowledge to remember it.
>
>  Also, this story is a limitation in the case of Transformer, and I don't know if this is a more universal story. On the other hand, there may be some theoretical background since the results are exactly the same for various architectures.
>
>  In the case of small LLMs, in addition to good quality data, artificially clean data can be created, and more important knowledge can be memorized by having those with fewer occurrences in the original data be exposed (paraphrased) many times.
>
>  For example, the example (2.1) in the paper contains 7 pieces of knowledge (triples) for 75 tokens, which is represented by about 10 tokens per piece of knowledge. It would take 10,000 tokens to expose one knowledge 1000 times. With 1 trillion tokens of training data, 100 million pieces of knowledge can be exposed 1,000 times.
>
>  In addition, this paper is an evaluation of knowledge expressed in triads, not other forms of knowledge, reasoning ability, etc.


---
This page is auto-translated from [/nishio/Physics of Language Models: Part 3.3, Knowledge Capacity Scaling Laws](https://scrapbox.io/nishio/Physics of Language Models: Part 3.3, Knowledge Capacity Scaling Laws) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
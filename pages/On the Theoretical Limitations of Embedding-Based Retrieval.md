---
title: "On the Theoretical Limitations of Embedding-Based Retrieval"
---

[Theoretical Limitations of Embedding-Based Search
[https://arxiv.org/abs/2508.21038](https://arxiv.org/abs/2508.21038)
    - [[Dense search]]

> [hillbig](https://x.com/hillbig/status/1962280460605862194) Although [[retrieval by embedded vectors]] has become popular in information retrieval, it has been shown to have theoretical limitations. That is, there is a limit to the number of document combinations that can be represented by the dimensionality d of the query and document vectors, indicating that there are "search tasks that can never be represented".
>
>  This limit can only be obtained if the degrees of freedom of the inner product matrix between documents and queries, expressed in the mathematical concept of sign-rank, d, is made quite large. For example, a 4k dimensional embedding cannot represent a document set of several hundred million or so (the search targets are often billions to tens of billions of documents).
>
>  We also designed a LIMIT dataset with a hypothetical problem set that is realistic and flexible. It consists of a who likes what document and a "who likes apples" query, covering all top-k combinations. Even with the latest embedding, very few RECALLs were given.
>
>  On the other hand, it was difficult with embedding, but can be solved with cross-encoders (do they encode and score both query and document at the same time?) and relanguages using them, and multi-vector, sparse models can also be solved.
>
>  Current academic benchmarks measure only a fraction of the query space and may over-learn (including problems that are essentially unsolvable, as above)
>
>  Comments
>  ===
>  Although the versatility of embedded vectors is widely used in information retrieval, from keyword search and full-text search, it has limitations as described above. There is a limitation because neighborhood search is pushed into a finite d-dimensional vector space (you can't push a complex traffic network into a 2-dimensional map).
>
>  On the other hand, it may be necessary to make sense of why this is the case towards the theoretically shown effective search in itself, even with the very limitations of this d-dimensional vector space. It may be an opportunity to capture the locality of the query space in actual retrieval, as well as redundancy and structure in human language and semantic space



---
This page is auto-translated from [/nishio/On the Theoretical Limitations of Embedding-Based Retrieval](https://scrapbox.io/nishio/On the Theoretical Limitations of Embedding-Based Retrieval) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
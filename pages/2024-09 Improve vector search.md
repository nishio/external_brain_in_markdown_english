---
title: "2024-09 Improve vector search"
---

2024-09-23
- Update based on kenn's post.

> [kenn](https://x.com/kenn/status/1826112390754349165) While cleaning up, we have also greatly revised the storage method of Vector Search DB @qdrant_engine. Disk usage and memory usage are now 1/10 of what they used to be!

> [kenn](https://x.com/kenn/status/1826112393455480944) First, we graduated from ada-002 to [[3-large]].
>
>  The number of dimensions has doubled from 1536 to 3072, but the new model can freely reduce the number of dimensions using the Matryoshka method, and even if the number is reduced to 256, the performance exceeds that of ADA.
>
>  There is a sense of increased efficiency in the use of manifold space, even physically, and this reduces the size to 1/6.
- [New embedding models and API updates | OpenAI](https://openai.com/index/new-embedding-models-and-api-updates/)
- What is Matryoshka?
    - [[Matryoshka Expression Learning]]
        - [[Matryoshka Representation Learning]]
            - [https://arxiv.org/abs/2205.13147](https://arxiv.org/abs/2205.13147)
            - > [koheiichi](https://x.com/koheiichi/status/1751408538453520750) The Matryoshka method is a method of creating an embedding vector so that part of the vector represents coarse-grained information of the entire original input, even if the length of the vector is changed. The Matryoshka method is a method to make sure that the representation is preserved even if the length of the vector is changed (even if some components are cut off).
            - >  > > Since the vector length of the new OpenAI embedding model is variable, it is > > expected that the Matryoshka method is used. It is expected that the Matryoshka method is used.
            - > ![image](https://gyazo.com/147cfea34aa4fde52f327bccc8fa5dab/thumb/1000)
        - [Matryoshka and Tropical | MaruLabo](https://www.marulabo.net/docs/matryoshka/)
        - [[[Brief AI Paper]] Matryoshka Representation Learning (Google)｜STEAM/acc []](https://note.com/steam0101/n/naaa7105cc3fb)
        - [What is Matryoshka Retriever? Dimensionality reduction speeds up the search!](https://zenn.dev/yokina_kaoto/articles/1155c6368c2a22)


> [kenn](https://x.com/kenn/status/1826112395397444041) Second, Qdrant's collections have a large overhead for each one (about 10MB?). So, if the number of stored vectors is small, it will be inefficient.
>  Vectors with the same dimensionality and payload schema can all be grouped into a single collection, and tenants can be separated by payload index to improve spatial efficiency at once.
>  [Qdrant 1.11 - The Vector Stronghold: Optimizing Data Structures for Scale and Efficiency - Qdrant](https://qdrant.tech/blog/qdrant-1.11.x/)
> ![image](https://gyazo.com/d1be87420bddb38dc6c923199062b9df/thumb/1000)


> [kenn](https://x.com/kenn/status/1826112398979379468) Furthermore, as the number of dimensions decreases from 1536 to 256, the size of the communicated JSON (12KB per 1000 dimensional vector assuming 12 characters per float) also decreases dramatically The most powerful high compression. High compression is the most powerful.
>
>  The final configuration is shared here. We think it is the best at this time in terms of both cosmetics and performance!
>  >[kenn](https://x.com/kenn/status/1825367360922103866) Here's a config template for @qdrant_engine for the multi-tenant setup:
>
>  - Create a single collection to store everything with the same vector dimensions, and filter by tenant ID at query time
>  - mmap() as many things as possible on disk to optimize memory usage
>  - defrag storage
>  ![image](https://pbs.twimg.com/media/GVUAUSwbAAAbOmU?format=jpg&name=medium#.png)

The vector size is 1/6, so you can make 5 derivatives from one sentence and stack them and the cost will not change (really?).
    - It would be interesting to create a variety of derivatives using an [[Extract questions at various levels of abstraction]] approach.
- Right now, it's implemented in a way that only allows it to be placed in a single chunked format, so I'd like to start with a form that makes it easier to do trial and error.

[[pVectorSearch]]

---
This page is auto-translated from [/nishio/2024-09ベクトル検索の改善](https://scrapbox.io/nishio/2024-09ベクトル検索の改善) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
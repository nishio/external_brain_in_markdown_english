---
title: "qdrant"
---

Qdrant - Vector Database
- [https://qdrant.tech/](https://qdrant.tech/)

[Collections - Qdrant](https://qdrant.tech/documentation/concepts/collections/)
> A collection is a named set of points (vectors with a payload) among which you can search. Vectors within the same collection must have the same dimensionality and be compared by a single metric.

[Payload - Qdrant](https://qdrant.tech/documentation/concepts/payload/)
> One of the significant features of Qdrant is the ability to store additional information along with vectors. This information is called payload in Qdrant terminology.
>  Qdrant allows you to store any information that can be represented using JSON.
- If you load the project name into the payload, you could search only or cross-search from a specific project.

[Points - Qdrant](https://qdrant.tech/documentation/concepts/points/)
- ID is a 64-bit integer, determined by the PUTting party
    - Whether to make it in terms of UUID or some other mechanism such as sequential numbers...
    - If you PUT the same ID, it will be overwritten.
    - Can specify conditions for payloads and retrieve all IDs that satisfy the conditions

[Search - Qdrant](https://qdrant.tech/documentation/concepts/search/)
- You could use a similarity score to cut off the footprint, but since you don't know what the appropriate threshold is, visualization of similarity is more likely to be better.

[Filtering - Qdrant](https://qdrant.tech/documentation/concepts/filtering/)
- "Match Any"
json

```json
{
  "key": "project",
  "match": {
    "any": ["aaa", "bbb"]
  }
}
```

- Full-text search matches are also available.
json

```json
{
  "key": "description",
  "match": {
    "text": "good cheap"
  }
}
```

    - If no index is created, the search is for substrings contained within

[Storage - Qdrant](https://qdrant.tech/documentation/concepts/storage/#storage)
- Vector Storage: In-memmory / memmap
- Payload Storage: InMemory / OnDisk
- [[RocksDB]] [RocksDB | A persistent key-value store | RocksDB](https://rocksdb.org/)
- If the payload is large, it is not practical to put it in memory.
- 1GB RAM on a minimal plan, and this Scrapbox JSON is 32MB, so we should just not worry about it and go on-memory for now!
    - If you try to put 1,000 cut and scanned books in it, it just barely overflows.
    - Well, we're going to start small first.

[Indexing - Qdrant](https://qdrant.tech/documentation/concepts/indexing/)
- Full text index tokenizer, from the description I doubt it will work properly for Japanese.
    - I'll give it a try.
        - [Quickstart - Qdrant](https://qdrant.tech/documentation/quick-start/)
        - [https://gist.github.com/nishio/111f11e078dd68768f5904ea879abe2f](https://gist.github.com/nishio/111f11e078dd68768f5904ea879abe2f)
        - I don't see any particular problem with a partial string match hit.
- Indexing Mechanism
    - > Qdrant currently only uses HNSW as a vector index. HNSW (Hierarchical Navigable Small World Graph) is a graph-based indexing algorithm.
    - [[HNSW]] ([[Hierarchical Navigable Small World Graph]])
        - [[Pinecore]] works the same way [Hierarchical Navigable Small Worlds (HNSW) | Pinecone](https://www.pinecone.io/learn/hnsw/).
        - [1603.09320 Efficient and robust approximate nearest neighbor search using Hierarchical Navigable Small World graphs](https://arxiv.org/abs/1603.09320)

![image](https://gyazo.com/66730fadc2491f94187fc5054f38d934/thumb/1000)
![image](https://gyazo.com/7fa11a66d9efe8c845339a477292308f/thumb/1000)
![image](https://gyazo.com/edcbeb002bc6bb08531c9ecea269f7f6/thumb/1000)
...
![image](https://gyazo.com/07bee77dd85fdd095bfb55421382d965/thumb/1000)


---
This page is auto-translated from [/nishio/qdrant](https://scrapbox.io/nishio/qdrant) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
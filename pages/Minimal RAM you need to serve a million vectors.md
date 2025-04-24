---
title: "Minimal RAM you need to serve a million vectors"
---

- [[vector search]] Talk about engine requirement RAM.

[Minimal RAM you need to serve a million vectors - Qdrant](https://qdrant.tech/articles/memory-consumption/)
<img src='https://scrapbox.io/api/pages/nishio-en/claude/icon' alt='claude.icon' height="19.5"/>
- If 1 million vectors are kept in memory, [[Qdrant]] requires about 1.2 GB of RAM
- Saving vectors to mmap file reduces RAM requirements to 600 MB
- In addition, HNSW graphs can also be mmap saved to provide 1 million vectors with 135 MB of RAM.
- However, disk performance has a significant impact on search speed. Using local SSD (IOPS=183k), search speed is 10 times faster than network storage (IOPS=6k).

[postgresql - How to calculate amount of RAM required for serving X N-dimensional vectors with pgvector (HNSW)? - Stack Overflow](https://stackoverflow.com/questions/77401874/how-to-calculate-amount-of-ram-required-for-serving-x-n-dimensional-vectors-with)
The above Qdrant article points out that the vector is 100 dimensional

---
This page is auto-translated from [/nishio/Minimal RAM you need to serve a million vectors](https://scrapbox.io/nishio/Minimal RAM you need to serve a million vectors) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
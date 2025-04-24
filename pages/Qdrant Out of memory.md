---
title: "Qdrant Out of memory"
---

2024-04-10
[[Qdrant]]
6:07 AM (7 hours ago)
to me

Hi there,

Thanks for using Qdrant cloud platform.

We saw that your Qdrant cluster nishio (df2a2a29-00d2-45a5-89e4-cfa4ead13db2) is running out of memory.

We'd like to help out here if needed. We could offer you the following:
- If you did not use memory mapped files yet, you can configure qdrant to put payload, index and more to disk and memmap it (might have a performance impact). Check our documentation here.
- If you can share some details on your use case we can probably also upgrade your RAM for free for a period of time till you are ready for production.

If you move to our regular paid standard tier clusters:
- you can scale your cluster up vertically to the next higher package here.
- we can scale your cluster horizontally by adding nodes and shifting shards

Please let us know if you have any questions or if we can help in any way.
Kind regards,

Qdrant Support

I scaled it up, yay or nay.
![image](https://gyazo.com/da4c7f739214bb04ad9d7d393fefd3de/thumb/1000)
I was just thinking about scaling up and making this Scrapbox data like [[⿻Plurality Assistant]].

---
This page is auto-translated from [/nishio/Qdrant Out of memory](https://scrapbox.io/nishio/Qdrant Out of memory) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Sum of the number of subsets of a subset"
---

The sum of the number of subsets of a subset of a set of size N is $3^N$
- The number of subsets of a set of size k is $2^k$
- How many subsets of size k are there in a set of size N → Combination of choosing k from N
    - Use [[binomial theorem]] in reverse
    - $\sum_{k=0}^N \binom{N}{k} 2^k = \sum_{k=0}^N \binom{N}{k} 2^k 1^{N-k} = (2 + 1)^N= 3^N$

---
This page is auto-translated from [/nishio/部分集合の部分集合の数の和](https://scrapbox.io/nishio/部分集合の部分集合の数の和) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
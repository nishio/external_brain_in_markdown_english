---
title: "Reciprocal Rank Fusion"
---

[Reciprocal rank fusion | Elasticsearch Guide 8.13 | Elastic](https://www.elastic.co/guide/en/elasticsearch/reference/current/rrf.html)
$score_i = {1\over a_i} + {1\over b_i}$
- Same as [[harmonic mean]] for large and small relationships
- $k$ may be added
    - ![image](https://gyazo.com/7fd3a17c5cc500f57a9a380e421765a1/thumb/1000)
        - [Reciprocal Rank Fusion outperforms Condorcet and individual Rank Learning Methods](https://plg.uwaterloo.ca/~gvcormac/cormacksigir09-rrf.pdf)(PDF)
        - Here k=60
    - Increasing k reduces the difference between first and second place.

---
This page is auto-translated from [/nishio/Reciprocal Rank Fusion](https://scrapbox.io/nishio/Reciprocal Rank Fusion) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
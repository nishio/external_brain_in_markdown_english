---
title: "ABC195F💻"
---

from [[ABC195]]
ABC195F
- Thoughts.
    - Factorize prime factors and choose prime factors with no overlap
    - There are 72 of them, so 2^72 ways.
    - Inclusion-elimination principle?
    - Considering after-events?
        - [[A collection of counting techniques]]
    - If we make a bipartite graph with prime factors and numbers, we can say that what we need to do is to find a bipartite matching
        - It seems that this is not the way to do it, since it is counting up, rather than seeking the largest one.
    - Bit with or without prime factor [[bitDP]]?
        - 2^72 is too big.
    - 72 is [[Special Constraints]].
    - Since it is a continuous integer, prime factors greater than 73 cannot appear twice.
    - We only need to think about prime numbers less than or equal to 72.
    - 20 prime numbers less than 72, does this work?
    - Official Explanation "This solution is fast enough."
- > [[COLOCON2018C]] difficult version [tw](https://twitter.com/kyopro_friends/status/1370734837565296642)

---
This page is auto-translated from [/nishio/ABC195F💻](https://scrapbox.io/nishio/ABC195F💻) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
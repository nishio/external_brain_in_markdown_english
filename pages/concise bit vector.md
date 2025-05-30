---
title: "concise bit vector"
---

[Concise Data Structures Part 2: Concise Data Structures for Bitvectors - Retrieva TECH BLOG](https://tech.retrieva.jp/entry/2020/07/30/125046)
[Concise data structure - Wikipedia](https://ja.wikipedia.org/wiki/%E7%B0%A1%E6%BD%94%E3%83%87%E3%83%BC%E3%82%BF%E6%A7%8B%E9%80%A0)

[Concise Bit Vector (Complete Dictionary) - Mister Miscellaneous](https://misteer.hatenablog.com/entry/bit-vector)
- Rank and select are constant time
    - This feature itself is OK with [cumulative sum
    - The feature is that it can be kept compact assuming the value range is 0/1
        - If the original range is small enough, the table pull will result in O(1)
            - Table of size 256 for 8 bits
        - If you keep track of the number of 1's (RANK) up to that point every 8 bits, it will be O(1) up to that point as well.
            - Compress this table itself one more step.
                - For example, record RANK every 512 bits.
                - [[Local, Express, Limited Express]] Idea


---
This page is auto-translated from [/nishio/簡潔ビットベクトル](https://scrapbox.io/nishio/簡潔ビットベクトル) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
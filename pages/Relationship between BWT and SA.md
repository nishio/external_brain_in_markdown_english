---
title: "Relationship between BWT and SA"
---

Relationship between [[BWT]] and [suffix array
- Consider cyclic shift $T[i..n$] instead of suffix $T[i..n$T[[0..i-1]]] sorted
    - Whichever way you sort, the order is the same.
- SA
    - Array of integers
    - means the starting position in the text of the cyclic shift
- BWT
    - character array
    - Meaning the letter L at the end of the cyclic shift
    - The first F of the cyclic shift is sorted, so sorting this array yields
    - We can build a mapping from L to F, and from here we can reconstruct the text.

---
This page is auto-translated from [/nishio/BWTとSAの関係](https://scrapbox.io/nishio/BWTとSAの関係) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
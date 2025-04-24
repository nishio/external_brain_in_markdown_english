---
title: "LCP array"
---

- [LCP array - Wikipedia](https://en.wikipedia.org/wiki/LCP_array)
- [Searching Suffix Array using LCP (Longest Common Prefix) - EchizenBlog-Zwei](https://echizen-tm.hatenadiary.org/entry/20110728/1311871765)
    - After creating [[suffix array]], record the length of the LCP (longest common prefix) of the adjacent string.
    - O(N) by the Kasai method
        - A Fast Algorithm Using Suffix Arrays for the Subword Counting Problem" [PDF](http://www-ikn.ist.hokudai.ac.jp/mthesis/H11_tohru_kasai_mastersthesis99_feb1999.pdf).
    - [https://naoyat.hatenablog.jp/entry/construct-suffix-array-and-lcp-in-linear-time](https://naoyat.hatenablog.jp/entry/construct-suffix-array-and-lcp-in-linear-time)
        - [http://www.nct9.ne.jp/m_hiroi/light/pyalgo60.html](http://www.nct9.ne.jp/m_hiroi/light/pyalgo60.html)
- The LCP length of any two items matches the minimum LCP length between the two
    - [[RMQ]]
- This information can be used to speed up the binary search.
    - When query length M, naive O(MlogN) becomes O(M+logN)

---
This page is auto-translated from [/nishio/LCP array](https://scrapbox.io/nishio/LCP array) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
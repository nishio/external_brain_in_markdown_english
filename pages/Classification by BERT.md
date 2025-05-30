---
title: "Classification by BERT"
---

- Convert a sentence into a vector with BERT
- For each element of a vector, make it 1-bit information by whether it is positive or negative.
- Select the elements in the order in which they are divided as much as possible into halves.
    - CART-like thinking
        - Select elements so that the decomposition reduces the Gini coefficient as little as possible.
        - [CART - "Toki no Mori Wiki" of Machine Learning](http://ibisforest.org/index.php?CART) #CART #Decision Tree
    - In this case, N=4000 or so, so if you choose 12 bits, you get one per bucket.
        - See also: [Localized sensitive hash - Wikipedia [https://ja.wikipedia.org/wiki/%E5%B1%80%E6%89%80%E6%80%A7%E9%8B%AD%E6%95%8F%E5%9E%8B%E3%83%8F%E3%83%83%E3%](https://ja.wikipedia.org/wiki/%E5%B1%80%E6%89%80%E6%80%A7%E9%8B%AD%E6%95%8F%E5%9E%8B%E3%83%8F%E3%83%83%E3%) 82%B7%E3%83%A5] #LSH
    - Hexadecimal notation would be a 3-character "category code".

- There is also a way to do it with [[kMeans]] #k-means
    - We need to save the location of the representative point.

- It's a hassle, so we'll try it in the first 12 dimensions for now.

---
This page is auto-translated from [/nishio/BERTで区分け](https://scrapbox.io/nishio/BERTで区分け) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
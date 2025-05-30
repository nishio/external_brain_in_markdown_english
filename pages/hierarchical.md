---
title: "hierarchical"
---

![image](https://gyazo.com/b97714f6de37e6a90043ceee1feea38c/thumb/1000)
- When each page of a book is the target document
    - Keywords appearing in each target have a larger DF, so [[TFIDF]] is smaller
- When a book is one target document
    - Keywords that appear on several pages in a book have a large TF and therefore a large TFIDF
- That is, it is affected in the opposite direction by the contour of the object.
    - Is there a scale that does not depend on the contours of the object?

- [Kernel density estimation - Wikipedia](https://ja.wikipedia.org/wiki/%E3%82%AB%E3%83%BC%E3%83%8D%E3%83%AB%E5%AF%86%E5%BA%A6%E6%8E%A8%E5%AE%9A)
- ${\displaystyle {\hat {f}}_{h}(x)={\frac {1}{nh}}\sum _{i=1}^{n}K\left({\frac {x-x_{i}}{h}}\right)}$
    - If the density estimation in the appropriate window is truly uniform in appearance, it should be uniformly distributed
    - Just look at the distance of the distribution from there.
    - The distance of the distribution is [Kullback-Leibler information content - Wikipedia [https://ja.wikipedia.org/wiki/%E3%82%AB%E3%83%AB%E3%83%90%E3%83%83%E3%82%AF%E3%83%BB%E3%83%A9%E3%82](https://ja.wikipedia.org/wiki/%E3%82%AB%E3%83%AB%E3%83%90%E3%83%83%E3%82%AF%E3%83%BB%E3%83%A9%E3%82) %A4%E3%83%96%E3%83%A9%E3%83%BC%E6%83%85%E5%A0%B1%E9%87%8F] or
    - ![image](https://gyazo.com/49118c094aa54a2aeb477367a37cd005/thumb/1000)
    - And one distribution is fixed.
    - Since we can ignore Q if we only consider large and small relationships
    - $\sum P(i) \log P(i)$
    - Oh, here [[negative entropy]], you can use this [[negative entropy]].
            - [[entropy]] (in the sense of [[entropy]])
        - $-\sum P(i) \log P(i)$

    - Suppose [[suffix array]] is created.
    - The position of the occurrence of a keyword can be determined by looking at the position of suffixes that begin with that keyword.
    - Can we get a density estimate from that?
        - Or can we skip density estimation and calculate entropy directly?
    - Assumed data size
        - 1000 books + blogs, etc., less than 1 GB
    - Miscellaneous Methods
        - Divide the entire document into bins of appropriate size and count the number of occurrences of keywords in each bin.
        - If the bin is 10000 and the keyword is 50 characters maximum and the count is 2 bytes, it's not much.
        - This counting process is O(N)
        - Finally, sort by entropy and see the results.


---
This page is auto-translated from [/nishio/文書が階層的](https://scrapbox.io/nishio/文書が階層的) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
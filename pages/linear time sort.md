---
title: "linear time sort"
---

    - [[bucket sort]]  [Wikipedia](https://ja.wikipedia.org/wiki/%E3%83%90%E3%82%B1%E3%83%83%E3%83%88%E3%82%BD%E3%83%BC%E3%83%88)
    - O(N+K) when there are K known possible values
        - Intuitive implementation: prepare a list of K items and put them into the list as they appear.
    - As a special case, when there are N ways, each of which appears only once, we can prepare an array of size N, O(N)
        - [[distributive sort]] 、 [[count sort]]
        - One of the implementation methods when sorting only the value to be sorted
        - Count the number of occurrences of each value
            - Since it is sufficient to know that "there are ni lists with the value i" without actually having a variable-length list with identical contents in memory
        - If obj is sorted by obj.x, this method is not possible because obj.x is not the same even if obj.x is the same.
    - Cases that can be ignored if the value is outside a certain range
        - If the sorting of values greater than or equal to 0 exceeds M, it is considered to be M, and so on.
        - After rounding off values outside the range, the number of possible values is fixed [[ABC023D]].

    - [[radix sort]] 、 [[laddix sort]]  [Wikipedia](https://ja.wikipedia.org/wiki/%E5%9F%BA%E6%95%B0%E3%82%BD%E3%83%BC%E3%83%88)
    - Sorting from the lower digits for values that are divided into 1-digit values
    - O(kN) with the number of digits as k
    - If d^k is somewhat small (about 10^6) when d is the number of possible values that can appear in each digit, bucket sorting is fine.
    - If the range of values is too large (about N), the number of digits k is logN and it ends up being O(NlogN)

    - [[insert sort]]  [Wikipedia](https://ja.wikipedia.org/wiki/%E6%8C%BF%E5%85%A5%E3%82%BD%E3%83%BC%E3%83%88)
    - O(N) for mostly aligned data

---
This page is auto-translated from [/nishio/線形時間ソート](https://scrapbox.io/nishio/線形時間ソート) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
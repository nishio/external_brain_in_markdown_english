---
title: "multiset in Python"
---

There is a common opinion that we want [[multiset]] in Python e.g. [[ABC170 E]].
Almost anything can be done in combination with [heapq

- [[heapq]]
    - Insert element with O(logn)
    - O(1) to obtain the minimum value
- Combination of [[heapq]] and dict (hash table) [[heapq+dict]].
    - [Data structures that can substitute multiset in Python - Tsubo's Competitive Pro Blog](https://tsubo.hatenablog.jp/entry/2020/06/15/124657)
    - O(logN) to insert or delete elements
    - O(1) to check existence of element and get minimum value
    - No bifurcation search.
- dichotomous search
    - If you are willing to pre-sort, [[bisect]].
        - The kth value is only read. o(1)
        - First place over k" is RIGHT, "first place over k" is LEFT
    - I want a fixed kth value -> [[heapq]].
        - [Summary of data structures for fast kth value retrieval - BIT on binary search, equilibrium binary search tree, etc. - Qiita](https://qiita.com/drken/items/1b7e6e459c24a83bb7fd)
        - [[Fennic tree]]  [[BIT]]
        - Size of value range D
        - Binary search O(logD)
        - Additions and deletions are O(logD)
            - Compressing D with [[coordinate compression]] is effective
        - Can be both the "kth value" and the "first value over k".
    - [[equilibrium binary tree]]
    - [[RBST]]
    - AVL Tree
        - [https://juppy.hatenablog.com/entry/2019/02/26/python_AVL木_配列ver_競技プログラミング_Atcoder_](https://juppy.hatenablog.com/entry/2019/02/26/python_AVL木_配列ver_競技プログラミング_Atcoder_)

- It is said that "ordered sets are faster in square partitioning" (unconfirmed).
    - [https://nagiss.hateblo.jp/entry/2019/06/04/220541](https://nagiss.hateblo.jp/entry/2019/06/04/220541)
        - [https://atcoder.jp/contests/abc140/submissions/7482671](https://atcoder.jp/contests/abc140/submissions/7482671)
- SkipList
    - [https://atcoder.jp/contests/arc033/submissions/14718760](https://atcoder.jp/contests/arc033/submissions/14718760)


- [C - Data Structure](https://atcoder.jp/contests/arc033/tasks/arc033_3)


- [[data structure]]

---
This page is auto-translated from [/nishio/Pythonでmultiset](https://scrapbox.io/nishio/Pythonでmultiset) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
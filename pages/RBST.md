---
title: "RBST"
---

Randomized Binary Search Tree
- [[ABC170 E]] Commentary on.
    - > Ordered multisets can be processed quickly by using C++ multisets, etc.
    - and therefore, what is the equivalent of multiset in C++ in Python? and the topic was raised
            - [[multiset in Python]] There are many cases where you can get by with heapq.
        - Python does not have [[equilibrium binary tree]] in the standard library
            - I felt like it would be a good idea to have it as my own library...

- Implementations that make nodes as objects are generally bad.
    - Because of the high cost of generating objects.
    - Implement in arrays and make with the policy to compile in numba.

- [AC](https://atcoder.jp/contests/abc170/submissions/14654208) on ABC170E


--- Development
- C++ implementation ported to Python
    - [Summary of data structures that can retrieve the kth value fast - such as BIT upper binary search and equilibrium binary search tree - Qiita](https://qiita.com/drken/items/1b7e6e459c24a83bb7fd), ported naively from
    - [https://github.com/nishio/atcoder/blob/master/memo/rbst_normal.py](https://github.com/nishio/atcoder/blob/master/memo/rbst_normal.py)
- Replace [[ABC170 E]] implementation in [[Fennic tree]] with RBST and verify AC in all test codes
    - Implementation in phoenix tree 4.83sec
    - Implementation in RBST 105.47sec
    - 20 times slower
- Remove class
    - 67.01sec
    - About 60% faster.
- Remove recurrence call and compile with [numba
    - 10.13sec
- Sequential addition in list changed to batch allocation in np.array
    - 4.60sec

---
This page is auto-translated from [/nishio/RBST](https://scrapbox.io/nishio/RBST) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
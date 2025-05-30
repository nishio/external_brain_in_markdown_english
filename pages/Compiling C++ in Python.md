---
title: "Compiling C++ in Python"
---

Using the fact that a Python program is executed twice in the AtCoder environment, the approach is to compile the extension module written in C++ the first time and import it the second time.
[https://atcoder.jp/contests/cpsco2019-s1/submissions/14705333](https://atcoder.jp/contests/cpsco2019-s1/submissions/14705333)
- [[multiset in Python]]

"Oh, the ultimate weapon?" but I'm worried about how much this will affect the cost of boxing.
- In terms of the simple speed of adding 1 million items, the C++ version is 529 ms, while the AVL tree implemented for PyPy is 495 ms, so it loses.
    - [https://github.com/nishio/atcoder/blob/master/multiset/cpp.py](https://github.com/nishio/atcoder/blob/master/multiset/cpp.py)
    - [https://github.com/nishio/atcoder/blob/master/multiset/pypyavl.py](https://github.com/nishio/atcoder/blob/master/multiset/pypyavl.py)
→I just did a cursory comparison, so I'd like to do a better comparison.

- [[Using C++ sets from Python]]

- [[Calling C++ from Python]]

---
This page is auto-translated from [/nishio/PythonでC++をコンパイル](https://scrapbox.io/nishio/PythonでC++をコンパイル) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Python Acceleration"
---

- 1: Devise an algorithm
- 2a: Run it with [PyPy
    - When there are many array subscript accesses, etc.
- 2b: Using [Numpy
    - When there are many batch operations on arrays
- 3a: AOT compilation in [[Numba]].
    - Fast if you get into it right, but still very limited in terms of data structures and libraries
    - Cannot be recursively called
- 3b: Write and compile in [Cython
    - Fast if written properly.
    - Writing properly is like writing a program in C.
- 3c: Writing libraries in C++

---
This page is auto-translated from [/nishio/Pythonの高速化](https://scrapbox.io/nishio/Pythonの高速化) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Numpy is not available in AtCoder's Cython."
---

cython

```
cimport numpy as np
```

:

```
./Main.c:600:10: fatal error: numpy/arrayobject.h: No such file or directory
  600 | #include "numpy/arrayobject.h"
      |          ^~~~~~~~~~~~~~~~~~~~~
compilation terminated.
```


Tried it on [Code Test - AtCoder Beginner Contest 172](https://atcoder.jp/contests/abc172/custom_test)

---
This page is auto-translated from [/nishio/AtCoderのCythonではNumpyが使えない](https://scrapbox.io/nishio/AtCoderのCythonではNumpyが使えない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
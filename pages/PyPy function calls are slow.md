---
title: "PyPy function calls are slow"
---

python

```
import sys

sys.setrecursionlimit(10**6)

def foo(x):
  if x == 0: return 0
  return foo(x - 1)

print(foo(10 ** 6 - 10))
```

Try it at [Code Testing - Educational DP Contest / DP Summary Contest](https://atcoder.jp/contests/dp/custom_test)
- Python: 653 ms runtime
- PyPy: 1154 ms runtime

#atcoder

---
This page is auto-translated from [/nishio/PyPyの関数呼び出しは遅い](https://scrapbox.io/nishio/PyPyの関数呼び出しは遅い) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
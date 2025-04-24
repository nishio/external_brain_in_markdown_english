---
title: "MemoryError in AtCoder's Python results in RE"
---

python

```
xs = [0] * (10 ** 9)
```

![image](https://gyazo.com/7a3c6eaea86deec2d0977e4c21e18fa7/thumb/1000)

In these cases, the Python processor throws a runtime exception before the memory limit is exceeded by actually allocating memory, saying that such an amount of memory cannot be allocated. Therefore, the display on the judge server is not MLE but RE.

---
This page is auto-translated from [/nishio/AtCoderのPythonでMemoryErrorを出すとREになる](https://scrapbox.io/nishio/AtCoderのPythonでMemoryErrorを出すとREになる) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
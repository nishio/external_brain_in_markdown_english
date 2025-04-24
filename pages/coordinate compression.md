---
title: "coordinate compression"
---

It would be easier to use Numpy, but I'm working on a policy of not using it, so I put it in the library.

python

```
class CoordinateCompression:
    def __init__(self):
        self.values = []

    def add(self, x):
        self.values.append(x)

    def compress(self):
        self.values.sort()
        x2i = {}
        for i, x in enumerate(self.values):
            x2i[x] = i
        self.x2i = x2i
        self.i2x = self.values
        return self.x2i, self.i2x
```


---
This page is auto-translated from [/nishio/座標圧縮](https://scrapbox.io/nishio/座標圧縮) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
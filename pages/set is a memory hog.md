---
title: "set is a memory hog"
---

The Python set eats 90 bytes per entry.
Around 10M entries, I get stuck on the 1024MB memory limit for [[atcoder]].
If the definition region is `[0, N)`, `np.zeros(N, np.bool_)` is good. It may be good to bring it into that form with [[Coordinate Compression]].

[[mprof]]
python

```
x = set()
for i in range(9_000_000):
    x.add(i)
```

- ![image](https://gyazo.com/afd0afef705664b82f9b3628c428add9/thumb/1000)

python

```
import numpy as np
x = np.zeros(9_000_000, np.bool_)
for i in range(9_000_000):
    x[i] = 1
```

- ![image](https://gyazo.com/e229d1c6443dd898728e827e4419e730/thumb/1000)

---
This page is auto-translated from [/nishio/setはメモリ食い](https://scrapbox.io/nishio/setはメモリ食い) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "median"
---

from [[heapq]]
median
- median
- Prepare queues in order of smallest upper half and largest lower half. Alternate the queues, and if the minimum value of the upper half exceeds the maximum value of the lower half, swap the queues.
python

```
from random import shuffle
xs = list(range(10))
shuffle(xs)
upper = []
lower = []
for i, x in enumerate(xs):
    if i % 2 == 0:
        heappush(upper, x)
    else:
        heappush(lower, -x)
        print(upper, lower)
        if -lower[0] > upper[0]:
            l = -lower[0]
            u = -upper[0]
            heapreplace(lower, u)
            heapreplace(upper, l)
            print(upper, lower)
print(upper[0], -lower[0])  # => 5 4
```


---
This page is auto-translated from [/nishio/中央値](https://scrapbox.io/nishio/中央値) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
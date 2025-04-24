---
title: "Getting the Best K"
---

from [[heapq]]
Getting the Best K
- If the size exceeds k, pop
python

```
from random import shuffle
xs = list(range(100))
shuffle(xs)
K = 3
queue = xs[:K]
heapify(queue)
for x in xs[K:]:
    heappush(queue, x)
    heappop(queue)
print(queue)  # => [97, 98, 99]
```



---
This page is auto-translated from [/nishio/Best Kの取得](https://scrapbox.io/nishio/Best Kの取得) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
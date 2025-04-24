---
title: "A value is added or deleted to a set. I want to get the smallest value."
---

from [[heapq]]
A value is added or deleted to a set. I want to get the smallest value.
→ Prepare a heapq that contains the deleted values and skip reading it when acquiring.
python

```
from heapq import *

added = []
removed = []
# add
heappush(added, 1)
heappush(added, 2)
# remove
heappush(removed, 1)
# get top
while removed and added[0] == removed[0]:
    heappop(added)
    heappop(removed)

print(added[0])  # => 2
```


---
This page is auto-translated from [/nishio/ある集合に値が追加削除される。最小の値を取得したい。](https://scrapbox.io/nishio/ある集合に値が追加削除される。最小の値を取得したい。) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
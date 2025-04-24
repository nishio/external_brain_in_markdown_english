---
title: "I want to update the Kth value of the heap."
---

from [[heapq]]
I want to update the Kth value of the heap.
-> rewrite, then _siftdown can be used to return to heap state with O(logN)
- However, this K is not the Kth in the sort order, so it is not useful. If you want to update an arbitrary value, it takes O(N) to find where that value is in the list.
    - see [[heapq+dict]]
- For example, if you want to "update the second largest value," you can use K=1,2, which is determined by comparing the two locations. I think so.
python

```
from heapq import _siftdown

queue = [1, 2, 3]
K = 1
queue[K] = -1
_siftdown(queue, 0, K)
print(queue)  # => [-1, 1, 3]
```


---
This page is auto-translated from [/nishio/ヒープのK番目の値を更新したい](https://scrapbox.io/nishio/ヒープのK番目の値を更新したい) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
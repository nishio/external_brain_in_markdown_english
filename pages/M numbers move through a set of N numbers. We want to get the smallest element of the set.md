---
title: "M numbers move through a set of N numbers. We want to get the smallest element of the set"
---

from [[heapq]]
There are N sets and M numbers that are different from each other and move from set to set. We want to get the smallest number in a set.
→ "which set you are in now" is stored separately in an array of size M. When leaving a set, it is not deleted from heapq. Same code for adding and moving. When retrieving an element, skip the elements that are not in the set.
python

```
N = 2
M = 2
items = [[] for _ in range(N)]
position = [-1] * M


def put(id, pos):
    heappush(items[pos], id)
    position[id] = pos


move = put


def top(pos):
    q = items[pos]
    while q:
        id = q[0]
        if position[id] != pos:
            heappop(q)
            continue
        return id
    return None


put(0, 0)
put(1, 0)

move(0, 1)
print(top(0))  # => 1
move(0, 0)
print(top(0))  # => 0
move(0, 1)
print(top(0))  # => 1
```


---
This page is auto-translated from [/nishio/M個の数がN個の集合を移動する。集合の最小要素を得たい](https://scrapbox.io/nishio/M個の数がN個の集合を移動する。集合の最小要素を得たい) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "N values are updated, I want to know the minimum value."
---

from [[heapq]]
There are N values and they are being updated, I want to know the minimum value.
→ Queue a tuple of which value was updated to what and when. Store the last modified time of the value in an array of size N. Skip information that is not up-to-date when retrieving.
python

```
N = 2
values = [None] * N
lastUpdate = [0] * N
queue = []
time = 0


def update(pos, value):
    global time
    time += 1
    values[pos] = value
    heappush(queue, (value, pos, time))
    lastUpdate[pos] = time


def top():
    while queue:
        value, pos, time = queue[0]
        if time == lastUpdate[pos]:
            return value
        heappop(queue)
    return None


update(0, 42)
print(top())  # => 42
update(1, 43)
print(top())  # => 42
update(0, 44)
print(top())  # => 43
```


---
This page is auto-translated from [/nishio/N個の値が更新される、最小値を知りたい](https://scrapbox.io/nishio/N個の値が更新される、最小値を知りたい) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Putting a guard on when loading a map"
---

Attach a wall at the point of loading map data.
- Top, bottom, left, right become `for d in [-1, +1, -WIDTH, +WIDTH]:`.
- The distance that can be moved at one time determines the width SENTINEL of the wall.
- Only SENTINEL is shifted for the starting point, etc.
    - Note that sometimes it is originally 1-origin.

[https://github.com/nishio/atcoder/blob/master/libs/readMap.py](https://github.com/nishio/atcoder/blob/master/libs/readMap.py)

Addendum in PAST5
- [[PAST5E]] I used to just read one, but this problem required me to read "two different widths of guard."
    - In addition, only one side is rotated, which is the source of the bug.
    - I made it a class, and I also made the rotation a method.
- [[PAST5H]]
    - It was necessary not to construct a grid graph.
- [[PAST5G]] "Maybe we could make a library of places to graph in terms of adjacencies," he wrote, but we should avoid graphing in the first place.

- [[Put the map in a 1D array]]


I made something that reads numpy before.
    - [[One-dimensional array with guard]]
- But if you think about it, when dealing with this kind of data, it is usually a random access to the map with subscripts.
- It is better to have it in a list than to wait with numpy because
    - see  [[NUMPY subscript access is slow.]]

---
This page is auto-translated from [/nishio/地図読み込み時に番兵をつける](https://scrapbox.io/nishio/地図読み込み時に番兵をつける) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
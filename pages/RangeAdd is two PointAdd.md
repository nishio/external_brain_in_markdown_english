---
title: "RangeAdd is two PointAdd"
---

[[Range Add Point Read]] can be realized with two Point Add and Range Sum using a regular [[segment tree]].
- If reads are in order from the top, you don't need to use a segment tree, just an array.
- If the range of values is 10^9 or something like that, it's difficult to use an array. You can use a dictionary. see [[ABC188]].


- with the difference between adjacent items, not the target array itself.
        - Inverse transformation of [cumulative sum
    - I wish this concept had a name, I see you call it [[incremental list]].
- Range Add is Point Add with start and end
:

```
def RangeAdd(start, end, value):
	PointAdd(start, value)
	PointAdd(end, -value)
```

- Point Read is the sum up to and including that position
:

```
def PointRead(pos):
	RangeSum(0, pos + 1)
```


- ![image](https://gyazo.com/a7c5788e15c7b7e45cf475276b6d63b2/thumb/1000)

[[Range Add]]

---
This page is auto-translated from [/nishio/RangeAddは二つのPointAdd](https://scrapbox.io/nishio/RangeAddは二つのPointAdd) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
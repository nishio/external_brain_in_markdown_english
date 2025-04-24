---
title: "numpy.unique"
---

python

```
>>> set(np.int64("1 2 3 1 4 2 0".split()))
{0, 1, 2, 3, 4}
>>> np.unique(np.int64("1 2 3 1 4 2 0".split()))
array([0, 1, 2, 3, 4])
```

set is a hash table, whereas this is a sorted np.array
[https://numpy.org/doc/stable/reference/generated/numpy.unique.html](https://numpy.org/doc/stable/reference/generated/numpy.unique.html)

Can [[dichotomous search]] with [numpy.searchsorted
> This function uses the same algorithm as the builtin python [[bisect]].bisect_left (side='left') and bisect.bisect_right (side='right') functions, which is also vectorized in the v argument.
[https://numpy.org/doc/stable/reference/generated/numpy.searchsorted.html](https://numpy.org/doc/stable/reference/generated/numpy.searchsorted.html)

[[numpy]]

---
This page is auto-translated from [/nishio/numpy.unique](https://scrapbox.io/nishio/numpy.unique) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
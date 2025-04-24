---
title: "numba contiguous array"
---

python

```
- Resolution failure for literal arguments:
reshape() supports contiguous array only
- Resolution failure for non-literal arguments:
reshape() supports contiguous array only

During: resolving callee type: BoundFunction(array.reshape for array(int64, 1d, A))
During: typing of call at main.py (225)


File "main.py", line 225:
    # def __repr__(self):
        <source elided>
    CD = data[2 * N:]
    AB = AB.reshape(-1, 2)
    ^
```


`i8[:]` to `i8[::1]`

[[numba]] contiguous array

---
This page is auto-translated from [/nishio/numba contiguous array](https://scrapbox.io/nishio/numba contiguous array) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
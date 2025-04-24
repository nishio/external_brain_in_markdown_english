---
title: "One-dimensional array with guard"
---

see  [[Putting a guard on when loading a map]]

from [[ABC170_F]]
Make a one-dimensional array of strings with [[sentry]] as long as they are newlines.
python

```
C = np.zeros((H + 2, W + 2), np.bool_)
C[1:-1, 1:-1] = np.frombuffer(read(), 'S1').reshape(H, -1)[:, :W] == b'.'
C = C.ravel()
H += 2
W += 2
```


- `ValueError: could not broadcast input array from shape (3,0) into shape (3,5)`
    - already read all data from stdin

Explanation of each step
python

```
>>> np.frombuffer(b"...\n.@.\n...\n", "S1")
array([b'.', b'.', b'.', b'\n', b'.', b'@', b'.', b'\n', b'.', b'.', b'.',
       b'\n'], dtype='|S1')
>>> _.reshape(3, -1)
array([[b'.', b'.', b'.', b'\n'],
       [b'.', b'@', b'.', b'\n'],
       [b'.', b'.', b'.', b'\n']], dtype='|S1')
>>> _[:,:3]
array([[b'.', b'.', b'.'],
       [b'.', b'@', b'.'],
       [b'.', b'.', b'.']], dtype='|S1')
>>> _ == b"."
array([[ True,  True,  True],
       [ True, False,  True],
       [ True,  True,  True]])
>>> C = np.zeros((3 + 2, 3 + 2), np.bool_)
>>> C[1:-1, 1:-1] = _
>>> C
array([[False, False, False, False, False],
       [False,  True,  True,  True, False],
       [False,  True, False,  True, False],
       [False,  True,  True,  True, False],
       [False, False, False, False, False]])
>>> C.ravel()
array([False, False, False, False, False, False,  True,  True,  True,
       False, False,  True, False,  True, False, False,  True,  True,
        True, False, False, False, False, False, False])
```


---
This page is auto-translated from [/nishio/番兵付きの一次元配列](https://scrapbox.io/nishio/番兵付きの一次元配列) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
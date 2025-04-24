---
title: "numba"
---

- [[RBST]]

![image](https://gyazo.com/72214310c3dffd3c4f2f73f55aa9c5a7/thumb/1000)

[Compiling code ahead of time — Numba 0.50.0.dev0+236.g64fbf2b-py3.7-linux-x86_64.egg documentation](https://numba.pydata.org/numba-doc/dev/user/pycc.html)

- The use of yield in a closure is unsupported.
    - NG: ` dist = min(distances[(goal, dir)] for dir in range(4))`

- `Untyped global name 'input': cannot determine Numba type of ...`
    - input is of unknown type and cannot be used, so read it and then pass it to the compiled function.

- You can't use defaultdict in NUMBA.
    - I tried to use dict, but I get type errors related to get.
    - To begin with, if you use a tuple as a key, it's a type error, so you need to pack it into an integer.
    - →Then let's be honest and use an array.
- [Supported Python features — Numba 0.50.0 documentation](https://numba.pydata.org/numba-doc/latest/reference/pysupported.html)
- [Supported NumPy features — Numba 0.50.0 documentation](https://numba.pydata.org/numba-doc/latest/reference/numpysupported.html)

Invalid use of type(CPUDispatcher(<function merge at 0x12be8de60>)) with parameters (array(int64, 1d, A), array(int64, 1d, A), array(int64, 1d, A), array(int64, 1d, A), array(int64, 1d, A), int64, int64, array(int64, 1d, A))

During: resolving callee type: type(CPUDispatcher(<function merge at 0x12be8de60>))
During: typing of call at rbst.py (96)
---
This page is auto-translated from [/nishio/numba](https://scrapbox.io/nishio/numba) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
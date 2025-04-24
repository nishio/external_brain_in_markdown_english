---
title: "PyPy/Cython funccall speed comparison"
---

2020-08-05
- Python3: 960 ms
- PyPy3: 92 ms
python

```
def f1(x):
    return x


def f2(x):
    ret = 0
    for i in range(10000):
        ret ^= f1(x)
    return ret

def f3(x):
    ret = 0
    for i in range(1000):
        ret ^= f2(x)
    return ret

print(f3(int(input())))
```


- 1000: PyPy3: 92 ms
- 10000: PyPy3: 164 ms
- 100000: PyPy3: 923 ms

- 1000: Cython: 387 ms
    - Huh? Surprisingly slow speed, huh? What am I getting wrong?
python

```
cdef f1(int x):
    return x


cdef f2(int x):
    cdef int ret = 0
    cdef int i
    for i in range(10000):
        ret ^= f1(x)
    return ret

  
cdef f3(int x):
    cdef int ret = 0
    cdef int i
    for i in range(1000):
        ret ^= f2(x)
    return ret

print(f3(int(input())))
```


---
This page is auto-translated from [/nishio/PyPy/Cython funccall速度比較](https://scrapbox.io/nishio/PyPy/Cython funccall速度比較) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
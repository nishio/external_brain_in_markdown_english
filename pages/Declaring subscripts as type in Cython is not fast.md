---
title: "Declaring subscripts as type in Cython is not fast"
---

Just type-declaring subscripts in [[Cython]] is not faster than [[PyPy]].
- Access to lists and arrays in Python and arrays in Numpy incurs the cost of creating subscript objects
- If the access target is a C array, it can be accessed directly in C. In this case, it is faster than PyPy.

Execution time summary
| Python | 285 ms | Original |
| -- | -- | -- |
| Cython | 316 ms | Original |
| PyPy | 82 ms | Original |
| Cython 173 ms subscripts are type-declared |
| Cython 137 ms list is type-declared |
| Cython 220 ms list to array |
| Cython CE list -> Numpy's np.array |
| Cython 25 ms list to C array |
All speeds are measured by AtCoder code tests.

---
First, the original code
python

```
N = 1000_000 
xs = [0] * N
for i in range(N):
  xs[i] = i
for i in range(1, N):
  xs[i] += xs[i - 1]

print(xs[N - 1])
```

Python 285 ms
Cython 316 ms
PyPy 82 ms

Type declaration for subscripts
:

```
cdef long i
```

Cython 173 ms
- Faster than raw Python, but not as fast as PyPy

Declare the list as type
:

```
cdef long i
cdef list xs
```

Cython 137 ms
- A little faster, but still not as good as PyPy.

The reason is that this `xs[i]` is completely different from C's array access, etc.
- Create a PyObject from a long value
- Increase the reference count by 1
- Call SetItem with it as an argument
- Handle various errors in between.
Because the process is called
Read the output C source and you'll see.
`$ cython -a -3 tiny_cython.pyx`
c

```c
+07:     xs[i] = i
    __pyx_t_2 = __Pyx_PyInt_From_int(__pyx_v_11tiny_cython_i); if (unlikely(!__pyx_t_2)) __PYX_ERR(0, 7, __pyx_L1_error)
    __Pyx_GOTREF(__pyx_t_2);
    if (unlikely(__pyx_v_11tiny_cython_xs == Py_None)) {
      PyErr_SetString(PyExc_TypeError, "'NoneType' object is not subscriptable");
      __PYX_ERR(0, 7, __pyx_L1_error)
    }
    if (unlikely(__Pyx_SetItemInt(__pyx_v_11tiny_cython_xs, __pyx_v_11tiny_cython_i, __pyx_t_2, int, 1, __Pyx_PyInt_From_int, 1, 1, 1) < 0)) __PYX_ERR(0, 7, __pyx_L1_error)
    __Pyx_DECREF(__pyx_t_2); __pyx_t_2 = 0;
  }
```


I thought it would be smarter to use array instead of list, but it turned out to be slower. Because it receives a list for initialization, it actually allocates space twice.
python

```
cdef long i
from cpython cimport array
import array as pyarray

N = 1000_000 
cdef array.array xs = pyarray.array("l", [0] * N)
for i in range(N):
  xs[i] = i
for i in range(1, N):
  xs[i] += xs[i - 1]

print(xs[N - 1])
```

220 ms
- I observed the C source for this one, too, and it was making PyInt with subscript access.

I can think of np.zeros as a way to allocate space by size instead of list...
python

```
cdef long i
import numpy as np
cimport numpy as np

N = 1000_000 
cdef np.ndarray xs = np.zeros(N, np.int32)
for i in range(N):
  xs[i] = i
for i in range(1, N):
  xs[i] += xs[i - 1]

print(xs[N - 1])
```

How [[Numpy is not available in AtCoder's Cython.]].
- I observed the C source at hand, and it was still making PyInt with subscript access.
    - Memory View needs to be created. see [Typed Memoryviews - Cython 3.0a5 documentation](http://docs.cython.org/en/latest/src/userguide/memoryviews.html)

Create an array of C
cython

```
cdef long i
cdef long[1000_000] xs

N = 1000_000
for i in range(N):
  xs[i] = i
for i in range(1, N):
  xs[i] += xs[i - 1]

print(xs[N - 1])
```

25 ms
- Finally faster than PyPy.
- The C source shows that it is just an array access.
c

```c
(__pyx_v_11tiny_cython_xs[__pyx_v_11tiny_cython_i]) = __pyx_v_11tiny_cython_i;
```

- Note that the size cannot be specified by a variable.
cython

```
cdef long N = 1000_000 
cdef long[N] xs
```

:

```
Main.pyx:3:11: Not allowed in a constant expression
```



There is one more way left to call malloc/free yourself.
- [Memory Allocation — Cython 3.0a5 documentation](https://cython.readthedocs.io/en/latest/src/tutorial/memory_allocation.html)

---
This page is auto-translated from [/nishio/Cythonで添え字を型宣言しても速くない](https://scrapbox.io/nishio/Cythonで添え字を型宣言しても速くない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
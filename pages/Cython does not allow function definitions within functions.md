---
title: "Cython does not allow function definitions within functions"
---

In Numba, "you can do it only if it's a recursive call," in Cython, "you can't define it there in the first place."

Considering the use in AtCoder, Numba is compiled function by function, so I would like it to be in one function, but Cython is compiled with the entire file converted to C, so it should be placed at the top level in a straightforward manner.

In that case, the local variable of the calling function cannot be accessed, so it must be passed as an argument or placed globally. The reason to avoid placing it globally in Python is that accessing local variables in Python is faster than accessing global variables, so there is no reason to avoid it in Cython.
- Related [[Local variables in Python are faster than global variables]].

cython

```
def main():
  cdef foo(long x):
    if x == 0: return 0
    return foo(x - 1) + x
  return foo(1000000)

main()
```

NG: `C function definition not allowed here`

cython

```
cdef foo(long x):
  if x == 0: return 0
  return foo(x - 1) + x

def main():
  return foo(1000000)

print(main())
```

OK

[[Cython]]

---
This page is auto-translated from [/nishio/Cythonでは関数内で関数定義ができない](https://scrapbox.io/nishio/Cythonでは関数内で関数定義ができない) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
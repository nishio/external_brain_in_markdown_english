---
title: "Passing complex types to NUMBA"
---

If you can do it in a straightforward np.array, that would be easier, but for practical purposes, there are complex types like "a dictionary whose keys are integers, and the values are lists of variable length. The elements of the list are tuples of two integers" (true story), and it's not feasible to try to pack them into np.array.

This type cannot be handled well by numba as a raw Python dictionary or list, but it can be achieved using typed.Dict and typed.List. The question is what happens to the function's type signature when passing this to the function.

If you look it up in numba.typeof.
- `DictType[int64,ListType[UniTuple(int64 x 2)]]`
but if this is written directly in the type signature, it will not work. The fix is
- `UniTuple(int64 x 2)` → `UniTuple(int64, 2)`
- `XXXType[xxx]` → `XXXType(xxx)`
(Maybe this is solved by eval without creating a parser. So you need to use Python-like syntax.)

There is also a way to have the typeof be inferred instead of a string.
python

```
@nb.jit(nb.typeof((1.0,1.0))(nb.double),nopython=True)
def f(a):
  return a,a
```


Now we can pass complex type values to numba compiled functions, which was our initial goal.

Added: atcoder's numba is 0.48 and old so it seems typed.List can't take arguments

python

```
import sys
import numba


def foo(x):
    for k in x:
        print("k:", k)
        for a, b in x[k]:
            print(a, b)


if sys.argv[-1] == "-c":
    # numba compile
    print("compiling")
    from numba.pycc import CC
    cc = CC('my_module')
    cc.export(
        'foo', 'void(DictType(int64,ListType(UniTuple(int64,2))))')(foo)
    cc.compile()
    exit()
else:
    x = numba.typed.Dict()
    x[1] = numba.typed.List([(1, 2), (3, 4)])
    x[100] = numba.typed.List([(100, 200)])

    if sys.argv[-1] == "-p":
        print(numba.typeof(x))
        # => DictType[int64,ListType[UniTuple(int64 x 2)]]
    else:
        from my_module import foo
        foo(x)
```


[[numba]]

---
This page is auto-translated from [/nishio/numbaに複雑な型を渡す](https://scrapbox.io/nishio/numbaに複雑な型を渡す) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
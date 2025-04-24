---
title: "Python Local Variables"
---

If there is an assignment to a name in a function, the name is determined to be a local variable of the function
Reading and writing the variable with and without assignment compiles to a different bytecode

python

```
In [1]: def foo():
   ...:     print(x)
   ...:     x = 10
   ...:     

In [2]: import dis

In [3]: dis.dis(foo)
  2           0 LOAD_GLOBAL              0 (print)
              2 LOAD_FAST                0 (x)
              4 CALL_FUNCTION            1
              6 POP_TOP

  3           8 LOAD_CONST               1 (10)
             10 STORE_FAST               0 (x)
             12 LOAD_CONST               0 (None)
             14 RETURN_VALUE

In [4]: def bar():
   ...:     print(x)
   ...:     

In [5]: dis.dis(bar)
  2           0 LOAD_GLOBAL              0 (print)
              2 LOAD_GLOBAL              1 (x)
              4 CALL_FUNCTION            1
              6 POP_TOP
              8 LOAD_CONST               0 (None)
             10 RETURN_VALUE
```


The global declaration has the effect of enforcing LOAD_GLOBAL/STORE_GLOBAL regardless of whether the assignment is made within a function or not.

python

```
In [6]: def foo():
   ...:     global x
   ...:     print(x)
   ...:     x = 10
   ...:     

In [7]: dis.dis(foo)
  3           0 LOAD_GLOBAL              0 (print)
              2 LOAD_GLOBAL              1 (x)
              4 CALL_FUNCTION            1
              6 POP_TOP

  4           8 LOAD_CONST               1 (10)
             10 STORE_GLOBAL             1 (x)
             12 LOAD_CONST               0 (None)
             14 RETURN_VALUE
```



---
This page is auto-translated from [/nishio/Pythonのローカル変数](https://scrapbox.io/nishio/Pythonのローカル変数) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
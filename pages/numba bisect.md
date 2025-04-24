---
title: "numba bisect"
---

python

```
from bisect import bisect
import numpy as np
import numba

# @numba.njit  # NG
def main(xs, x):
    print(bisect(xs, x))

main(np.arange(10), 3)  # => 4
```


OK
python

```
...
from bisect import bisect
import numpy as np
import numba


@numba.njit
def bisect(a, x, lo=0, hi=None):
    ...


@numba.njit
def main(xs, x):
    print(bisect(xs, x))
... 
```



adding a signature would involve implementing it for Numba
[http://numba.pydata.org/numba-doc/latest/extending/index.html](http://numba.pydata.org/numba-doc/latest/extending/index.html)
And [http://numba.pydata.org/numba-doc/latest/extending/overloading-guide.html](http://numba.pydata.org/numba-doc/latest/extending/overloading-guide.html)

NG
python

```
from numba.pycc import CC
cc = CC('my_module')

@cc.export("bisect", "i8(i8[:], i8)")
def bisect(a, x):
   ...
@cc.export("main", "i8(i8[:], i8)")
def main(xs, x):
   ...

cc.compile()
```



[[numba]] [[bisect]]

---
This page is auto-translated from [/nishio/numba bisect](https://scrapbox.io/nishio/numba bisect) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
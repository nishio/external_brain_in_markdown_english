---
title: "Turn a sequence of numbers into a rational expression"
---

    - [[sequence]] and [[formal power series]] correspond, and [[convolution]] and multiplication in each world correspond
- Convolution of sequences of numbers can be easily experimented with ([[np.convolve]])
- If the sequence of numbers can be simplified to a simple form by repeating the appropriate convolution, a formal power series with infinite terms can be reduced to a rational expression with a finite number of terms.
- The Nth order term in the rational expression is obtained by O(log N)
    - That is, the Nth term of the sequence is found by O(log N) see [[Two Snuke#5f0afb00aff09e00009b591e]].

![image](https://gyazo.com/2060b6bfdb5a263b0096e09cd076395f/thumb/1000)


python

```
In [43]: xs
Out[43]: 
array([   0,    1,    2,    4,    6,    9,   12,   16,   20,   25,   30,
         36,   42,   49,   56,   64,   72,   81,   90,  100,  110,  121,
        132,  144,  156,  169,  182,  196,  210,  225,  240,  256,  272,
        289,  306,  324,  342,  361,  380,  400,  420,  441,  462,  484,
        506,  529,  552,  576,  600,  625,  650,  676,  702,  729,  756,
        784,  812,  841,  870,  900,  930,  961,  992, 1024, 1056, 1089,
       1122, 1156, 1190, 1225, 1260, 1296, 1332, 1369, 1406, 1444, 1482,
       1521, 1560, 1600, 1640, 1681, 1722, 1764, 1806, 1849, 1892, 1936,
       1980, 2025, 2070, 2116, 2162, 2209, 2256, 2304, 2352, 2401, 2450,
       2500])
```


python

```
In [44]: import numpy as np
In [45]: from functools import reduce

In [48]: reduce(np.convolve, [[1, -1]] * 1, xs)[:10]
Out[48]: array([0, 1, 1, 2, 2, 3, 3, 4, 4, 5])

In [49]: reduce(np.convolve, [[1, -1]] * 2, xs)[:10]
Out[49]: array([0, 1, 0, 1, 0, 1, 0, 1, 0, 1])

In [52]: reduce(np.convolve, [[1, -1]] * 2 + [[1, 0, -1]], xs)[:10]
Out[52]: array([0, 1, 0, 0, 0, 0, 0, 0, 0, 0])
```


python

```
In [53]: reduce(np.convolve, [[1, -1]] * 2 + [[1, 0, -1]], [1])
Out[53]: array([ 1, -2,  0,  2, -1])
```


---
This page is auto-translated from [/nishio/数列を有理式にする](https://scrapbox.io/nishio/数列を有理式にする) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
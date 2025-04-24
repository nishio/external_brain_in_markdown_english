---
title: "bit operation"
---

[Subset representation with bit strings [[Bitwise Arithmetic Techniques Advent Calendar 2016 Day 1]] - prime's diary []](https://primenumber.hatenadiary.jp/entry/2016/12/01/000000)
    - [[fast zeta transformation]]   [[fast Möbius transformation]]   [[convolution]]

S's i-th is 1?
- `(S >> j) & 1`
- 0-origin and 0 is LSB

Whole set of N elements
- `(1 << N) - 1`

Complementary set (whole set as U)
- `~S & U`

rightmost 1
- `(x & -x)`

Double loop for elements of a given set
python

```
def calcScore(S):
    x = S
    ret = 0
    i = 0
    while x:
        if x & 1:
            for j in range(i):
                if (S >> j) & 1:
                    ret += M[i, j]
        x //= 2
        i += 1
    return ret
```


[[subset enumeration]] of the given set
python

```
def solve(S):
    x = S
    while x > 0:
        print(f"{x:08b}")
        x = (x - 1) & S
```


Is T included in S?
- The common part with the complement of S is empty.
- `~S & T == 0`

Number of 1's (popcount)
- If 32 bits.
c

```c
T = (T & 0x55555555) + ((T >>  1) & 0x55555555);
T = (T & 0x33333333) + ((T >>  2) & 0x33333333);
T = (T & 0x0F0F0F0F) + ((T >>  4) & 0x0F0F0F0F);
T = (T & 0x00FF00FF) + ((T >>  8) & 0x00FF00FF);
T = (T & 0x0000FFFF) + ((T >> 16) & 0x0000FFFF);
```

c

```c
T -= (T >> 1) & 0x55555555;
T = (T & 0x33333333) + ((T >> 2) & 0x33333333);
T = (T + (T >> 4)) & 0x0F0F0F0F;
T = (T * 0x01010101) >> 24;
```


![image](https://gyazo.com/d5c5b3c6c77c4b5b267f2905ab413398/thumb/1000)


---
This page is auto-translated from [/nishio/ビット演算](https://scrapbox.io/nishio/ビット演算) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
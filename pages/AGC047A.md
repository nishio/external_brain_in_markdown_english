---
title: "AGC047A"
---

AC
[A - Integer Product](https://atcoder.jp/contests/agc047/tasks/agc047_a)
![image](https://gyazo.com/e7dec806a945dce731880ce2d2c75d8e/thumb/1000)
- I avoided using floating point numbers and multiplied them by 10^9 to make them integers.
    - The problem condition would be "Multiply an integer by a multiple of 10^18."
    - Calculate how many times each number is divisible by 2 (P2) and how many times each number is divisible by 5 (P5).
    - `P2[i] + P2[j] > 17 and P5[i] + P5[j] > 17` then "multiply by 10^18"
python

```
def solve1(N, AS):
    ret = 0
    P2 = []
    P5 = []
    for i in range(N):
        p2 = 0
        p5 = 0
        x = AS[i]
        while x % 2 == 0:
            p2 += 1
            x //= 2
        while x % 5 == 0:
            p5 += 1
            x //= 5
        P2.append(p2)
        P5.append(p5)

    for i in range(N):
        for j in range(i + 1, N):
            if P2[i] + P2[j] > 17 and P5[i] + P5[j] > 17:
                ret += 1
    return ret
```


This will AC for small data, but TLE for large data.
- Since there are up to 200,000 in number, the method of comparing them one by one is on the order of 10 billion, so it's a TLE.
    - There should not be a double loop of N
    - Pre-processing allows this to be done in a single loop.
    - That is, given `P2[i], P5[i]`, it is sufficient to know "the number of j's satisfying `P2[i] + P2[j] > 17 and P5[i] + P5[j] > 17`" without looping
    - → Create [frequency table
- According to the description, that alone would be AC.
    - The width of the frequency distribution table is at most 19
        - Because there's no need to distinguish between the 18 squares and above.
    - The number of calculations is about 200,000 x 400, which is narrow enough
- But I didn't notice, and I got even more creative.
    - By calculating the [[cumulative sum]] in advance, the "number of j's satisfying `P2[i] + P2[j] > 17 and P5[i] + P5[j] > 17`" can be obtained without even a loop in the frequency table.
    - With Numpy, [[Cumulative sum of two-dimensional arrays]] is also easy
python

```
for i in range(19, 0, -1):
    P[i - 1] += P[i]
for i in range(19, 0, -1):
    P[:, i - 1] += P[:, i]
```

- Now you can ask for it in a single loop.
python

```
for i in range(N):
    ret += P[18 - P2[i], 18 - P5[i]]
```

- But this is not the correct answer and needs to be corrected.
    - First, both P2 and P5 have counted "themselves" as a pair for numbers over 9, so subtract that
    - As for the rest, both ij and ji pairs are counted, so divide by 2.
- This will make it right.

python

```
def solve(N, AS):
    import numpy as np
    ret = 0
    P2 = []
    P5 = []
    P = np.zeros((20, 20), dtype=np.int)

    for i in range(N):
        p2 = 0
        p5 = 0
        x = AS[i]
        while x % 2 == 0:
            p2 += 1
            x //= 2
        while x % 5 == 0:
            p5 += 1
            x //= 5
        if p2 > 18:
            p2 = 18
        P2.append(p2)
        P5.append(p5)
        P[p2, p5] += 1

    for i in range(19, 0, -1):
        P[i - 1] += P[i]
    for i in range(19, 0, -1):
        P[:, i - 1] += P[:, i]

    for i in range(N):
        ret += P[18 - P2[i], 18 - P5[i]]
    ret -= P[9, 9]
    ret //= 2
    return ret
```



---
This page is auto-translated from [/nishio/AGC047A](https://scrapbox.io/nishio/AGC047A) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
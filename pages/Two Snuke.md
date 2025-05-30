---
title: "Two Snuke"
---

[F - Two Snuke](https://atcoder.jp/contests/aising2020/tasks/aising2020_f)
    - [[AISING Programming Contest 2020]]
- [Commentary by maspy [https://maspypy.com/atcoder-%E5%8F%82%E5%8A%A0%E6%84%9F%E6%83%B3-2020-07-11%E3%82%A8%E3%82%A4%E3%82%B7%E3%83%B3%E3%82](https://maspypy.com/atcoder-%E5%8F%82%E5%8A%A0%E6%84%9F%E6%83%B3-2020-07-11%E3%82%A8%E3%82%A4%E3%82%B7%E3%83%B3%E3%82) I want to understand%B0-%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9F%E3%83%B3%E3%82%B0-%E3%82%B3%E3%83%B3%E3%83%86#toc5]

question (e.g. on a test)
![image](https://gyazo.com/f9dd32211e6deb0099516ea09a18ca4f/thumb/1000)
- N is given by the problem condition.
- For n less than or equal to N, divide it into 5 numbers
- Focusing on this one, let m be the number
- Divide this m into two numbers i, j
    - $i + j = m$
    - where the constraint [$ 0 \le i < j
- I want to find the sum of the differences for all possible i,j
    - $f(m) = \sum_{i,j} j - i$
    - I sought it on my own up to this point, but I couldn't figure out where to go from here.
python

```
def f(x):
    return (x + x % 2) * ((x + 2) // 2) // 2
```


Solving with formal power series
- Since this function f is a function that takes natural numbers as arguments, it can be interpreted as a sequence of numbers
- A sequence of numbers corresponds to a [[formal power series]] which is its [[generating function]], let F
    - $F = \sum_{m=0}^\infty f(m)$
    - My implementation of f would have caused a remainder or truncation, but if we can express this in rational expressions, we can use the formal power series tool.
    - Observe a sequence of numbers
python

```
In [85]: np.array([f(x) for x in range(0, 100)])
Out[85]: 
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

    - I'm writing the general term in code, so I know that even-oddness affects it, so I'll try to separate them.
python

```
In [94]: fs[::2]
Out[94]: 
array([   0,    2,    6,   12,   20,   30,   42,   56,   72,   90,  110,
        132,  156,  182,  210,  240,  272,  306,  342,  380,  420,  462,
        506,  552,  600,  650,  702,  756,  812,  870,  930,  992, 1056,
       1122, 1190, 1260, 1332, 1406, 1482, 1560, 1640, 1722, 1806, 1892,
       1980, 2070, 2162, 2256, 2352, 2450])

In [95]: fs[1::2]
Out[95]: 
array([   1,    4,    9,   16,   25,   36,   49,   64,   81,  100,  121,
        144,  169,  196,  225,  256,  289,  324,  361,  400,  441,  484,
        529,  576,  625,  676,  729,  784,  841,  900,  961, 1024, 1089,
       1156, 1225, 1296, 1369, 1444, 1521, 1600, 1681, 1764, 1849, 1936,
       2025, 2116, 2209, 2304, 2401, 2500])
```

    - At the time of this observation, maspy wrote that $F = \frac{P}{(1-x^2)^3}$ was fixed, but I didn't understand it, so I'll bite

sequence of numbers skipped one by one
- 1, 0, 1, 0, ... How to express the sequence of numbers "0, 0, 1, 0, ..." in terms of a formal power series
- If we naively write the equation
- $G = 1 + x^2 + x^4 + \ldots = \sum_{n=0}^\infty x^{2n}$
    - [Infinite sum compression using the inverse of a formal power series
- $G = 1 + x^2 + x^4 + \ldots$
- $x^2G = x^2 + x^4 + \ldots$
- $(1-x^2)G = 1$
- $G = 1/(1-x^2)$

One skipped square number
- 0, 1, 0, 4, 0, 9, ... How to express the sequence of numbers "0, 0, 4, 0, 0, 9, ..." in terms of a formal power series
- This is $H = \sum_{n=0}^\infty ((n+1) / 2)^2 x^n$ with only the odd-numbered th taken
    - Note that I was confused as to whether the number sequence was 1-origin or 0-origin, so I aligned it with 0.
- Pulled $F - H$.
python

```
In [101]: fs = np.array([f(x) - ((x+1)/2)**2 for x in range(100)])
In [102]: fs
Out[102]: 
array([-0.25,  0.  , -0.25,  0.  , -0.25,  0.  , -0.25,  0.  , -0.25,
        0.  , -0.25,  0.  , -0.25,  0.  , -0.25,  0.  , -0.25,  0.  ,...
```


- That is, $F = G / 4 + H$.
    - Since the calculation is tedious, let's multiply everything by 4 and assume 4H=J.
    - $4F = G + J$
    - $J = \sum_{n=0}^\infty (n+1)^2 x^n$
    - The first time I did it, I was doing a [[miscalculation]], and it gave me an incorrect equation down the road.
python

```
In [35]: reduce(np.convolve, [[1, -1]] * 0,  np.array([(x + 1) ** 2 for x in range(100)]))[:20]
Out[35]: 
array([  1,   4,   9,  16,  25,  36,  49,  64,  81, 100, 121, 144, 169,
       196, 225, 256, 289, 324, 361, 400])

In [36]: reduce(np.convolve, [[1, -1]] * 1,  np.array([(x + 1) ** 2 for x in range(100)]))[:20]
Out[36]: 
array([ 1,  3,  5,  7,  9, 11, 13, 15, 17, 19, 21, 23, 25, 27, 29, 31, 33,
       35, 37, 39])

In [37]: reduce(np.convolve, [[1, -1]] * 2,  np.array([(x + 1) ** 2 for x in range(100)]))[:20]
Out[37]: array([1, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2, 2])

In [38]: reduce(np.convolve, [[1, -1]] * 3,  np.array([(x + 1) ** 2 for x in range(100)]))[:20]
Out[38]: array([1, 1, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0])
```

    - $J = \frac{1 + x}{(1-x)^3}$
    - Did (1-x)^3 correspond to taking the difference three times?
    - $4F = G + J = \frac{1}{1-x^2} + \frac{1 + x}{(1-x)^3} = \frac{(1 - x)^2 + (1 + x)^2}{(1 + x)(1 - x)^3} = \frac{4x}{(1 + x)(1 - x)^3}$

I need a simpler formula.
- Try what maspy is doing "multiply because (1-x) is likely to come in the denominator" [[Turn a sequence of numbers into a rational expression]].
    - The product of a formal power series is the convolution of a sequence
    - Using np.convolve, the calculation can be done in one line.
python

```
In [120]: reduce(np.convolve, [[1, -1], [1, -1], [1, -1], [1, 1]], fs)
Out[120]: 
array([    0,     1,     0,     0,     0,     0,     0,     0,     0, ...
```

        - Multiplying (1 - x)(1 - x)(1 - x)(1 - x)(1 + x) leaves x
        - $\frac{x}{(1-x)^3(1+x)}$
- Did I make a miscalculation along the way? I will verify later.
- By the way, I multiplied $(1-x^2)^3$ as maspy originally said, and got this
python

```
In [121]: reduce(np.convolve, [[1, 0, -1], [1, 0, -1], [1, 0, -1]], fs)
Out[121]: 
array([    0,     1,     2,     1,     0,     0,     0,     0,     0, ...
```

    - $\frac{x(1 + 2 x + x^2)}{(1-x^2)^3} = \frac{x(1 + x)^2}{(1-x)^3(1+x)^3} = \frac{x}{(1-x)^3(1 + x)}$
    - Sort it out and the result is the same.

Suppose F is obtained.
- $F = \frac{x}{(1-x)^3(1+x)}$
- F was a power series for one of the five separate blocks.
    - This could be interpreted as a function with m as an argument, and the answer was when the sum was m
        - $[x^m]F = f(m) = \sum_{i,j} j - i$
- $[x^n]F^5$ is the answer when the sum of the 5 blocks is n
- Since the problem condition is "when the sum is less than or equal to N," the final answer we want to obtain is
    - $[x^n] \sum_{n=0}^{\infty} F^5$
- What does this summing part have to do with dividing by (1-x)?
        - I thought it was [[Infinite sum compression using the inverse of a formal power series]], but it's not...
    - Dividing by (1-x) means multiplying by [$ \sum_{n=0}^\infty x^n
    - The product of formal power series is the convolution of a sequence of numbers. Since we are convolving with a sequence of all 1's, the Nth term of the convolution result is the sum of the original sequence up to N
    - $\sum_{n=0}^{\infty} F^5 = F^5 / (1-x) = \frac{x^5}{(1-x)^{16}(1+x)^5}$
Now that we have determined the formal power series we need to find, the next step is to solve for it
- Looks good if you understand and implement [polynomial remainder](http://q.c.titech.ac.jp/docs/progs/polynomial_division.html)
- First, define a function that passes through only even/odd dimensions of a formal power series
    - $\mathcal{E}(G(x)) = \frac{G(x) + G(-x)}{2}$
    - $\mathcal{O}(G(x)) = \frac{G(x) - G(-x)}{2}$
    - In short, when mirrored and added together on the x-axis, the odd functions cancel each other out and disappear.
    - Here, (x) is specified for the sake of explanation, but omitted hereafter, $G^* = G(-x)$.
- $[x^n]F = P/Q$(Q(0)=1)
    - When n=0
    - $[x^n]F = P(0)$
        - This is the loop termination condition
    - When n is an even number
    - $[x^n]F = [x^n]\mathcal{E}(F)$
    - $= [x^n](\frac{P}{Q} + \frac{P^*}{Q^*})/2$
    - $= [x^n](\frac{PQ^* + P^*Q}{QQ^*})/2$
    - $= [x^n](\frac{\mathcal{E}(PQ^*)}{QQ^*})/2$
    - When n is odd
    - $[x^n]F = [x^n]\mathcal{O}(F)$
    - $= [x^n](\frac{P}{Q} - \frac{P^*}{Q^*})/2$
    - $= [x^n](\frac{PQ^* - P^*Q}{QQ^*})/2$
    - $= [x^n](\frac{\mathcal{O}(PQ^*)}{QQ^*})/2$
    - At this time $QQ^*$ is an even function
        - $Q = q_0 + q_1x + q_2 x^2 + ...$ ...] and let
        - $Q^* = q_0 - q_1x + q_2 x^2 + ...$ because the terms of odd order disappear when multiplied by
        - In other words, as a sequence of numbers, the odd-numbered sequence is a sequence of skipped zeros.
        - We can make a compressed Q' of this.
            - such as $Q'(x^2) = QQ^*$
            - Since it's a product of formal power series, it can be implemented by convolving a sequence of numbers, and you can just skip ahead and read it.
        - Similarly, numerators can be compressed because they are a sequence of skipped numbers.
        - $P_e(x^2) = \mathcal{E}(PQ^*)$
        - $P_o(x^2) = \mathcal{O}(PQ^*) / x$

Implementation [AC](https://atcoder.jp/contests/aising2020/submissions/15210464)
- maspy found and used a more compact denominator, probably by searching at hand(misunderstanding)
    - but since it is an aupart, I used $\frac{x^5}{(1-x)^{16}(1+x)^5}$ as I have done so far.

    - I was mistaken when I saw `[1,-2,0,2,-1]` in the code below, but the formula was the same
python

```
den = np.array([1,-1], np.int64)
for _ in range(5):
    den = np.convolve(den, np.array([1,-2,0,2,-1]))
```

    - This was an expansion of [$ (1-x)^3(1+x)
python

```
In [287]: reduce(np.convolve, [[1, -1]] * 3 + [[1, 1]], [1])
Out[287]: array([ 1, -2,  0,  2, -1])
```

- maspy used a fast convolution using FFT, but I was too tired to read that one.
    - I tried to use np.convolute, but it overflowed int64, so I had no choice but to create my own
- `Qm`: $Q^*$
    - Just sign-reverse the odd-order coefficients of Q
    - `Qm = Q.copy()` `Qm[1::2] *= -1`
python

```
def solve(N):
    Q = reduce(
        np.convolve,
        [[1, -1]] * 16 + [[1, 1]] * 5,
        np.array([1], dtype=np.int64))
    P = np.zeros(6, dtype=np.int64)
    P[5] = 1

    def conv(X, Y):
        n = X.shape[0]
        m = Y.shape[0]
        ret = np.zeros(n + m - 1, dtype=np.int64)
        for i in range(n):
            ret[i:i + m] += X[i] * Y
            ret[i:i + m] %= MOD
        return ret

    while N:
        Qm = Q.copy()
        Qm[1::2] *= -1
        QQm = conv(Q, Qm)
        PQm = conv(P, Qm)
        if N % 2:
            P = PQm[1::2]
        else:
            P = PQm[::2]
        Q = QQm[::2]
        N //= 2
    return P[0]
```


---
This page is auto-translated from [/nishio/Two Snuke](https://scrapbox.io/nishio/Two Snuke) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
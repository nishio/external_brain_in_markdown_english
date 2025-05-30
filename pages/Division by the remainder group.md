---
title: "Division by the remainder group"
---

Given a large prime number N and appropriate numbers K and R, we want to find x such that the remainder of Kx in N is R.
- `Kx mod N = R`

This is equivalent to dividing K by R in [[remainder group]]. [[irreducible surplus class]].
- It can be interpreted as finding the [[Inverse Element in mod P]] of K and multiplying it by R
- Don't simply divide.
    - Example 2x mod 7=1 the answer is 4

First, solve for R=1.
- Use [[Euclid's reciprocal division]] for N and K
- However, the goal is not to find the greatest common divisor.
    - We know that the greatest common divisor is 1 because N is a prime number.
- The objective is to express 1 as a linear combination of N and K
    - Form of `aN + bK == 1`.
    - Since aN vanishes mod N $bK \equiv 1 \pmod{N}$
        - So b is the inverse of K in mod N
        - [[Extended Euclidean reciprocal division]]

Multiply both sides of the resulting equation by R to obtain the desired division result

python

```
def mod_inverse_ee(a, m):
    """
    Solve ax mod m = 1 with extended euclidean.
    x = a^-1.
    """
    x, y, g = extended_euclidean(a, m)
    assert g == 1
    return x % m
 
def extended_euclidean(a, b, test=False):
    """
    Extended Euclidean algorithm
    Given a, b, solve:
    ax + by = gcd(a, b)
    Returns x, y, gcd(a, b)

    Other form, for a prime b:
    ax mod b = gcd(a, b) = 1

    >>> extended_euclidean(3, 5, test=True)
    3 * 2 + 5 * -1 = 1 True
    >>> extended_euclidean(240, 46, test=True)
    240 * -9 + 46 * 47 = 2 True

    Derived from https://atcoder.jp/contests/acl1/submissions/16914912
    """
    init_a = a
    init_b = b
    s, u, v, w = 1, 0, 0, 1
    while b:
        q, r = divmod(a, b)
        a, b = b, r
        s, u, v, w = v, w, s - q * v, u - q * w

    if test:
        print(f"{init_a} * {s} + {init_b} * {u} = {a}",
              init_a * s + init_b * u == a)
    else:
        return s, u, a
```





--- old version 2020/06/18
python

```
"""
Given K, N, R, find x s.t. Kx mod N = R
"""
R = 1234567

# Solve Kx + Ny = 1
N = 9999991
K = 2236206
a = N
b = K
vec = [(1, 0), (0, 1)]  # b = 0 N + 1 K
while True:
    q = a // b
    r = a % b
    # print(q, r)
    (aa, ab), (ba, bb) = vec
    vec = [(ba, bb), (aa - q * ba, ab - q * bb)]
    # print(vec)
    if r == 1:
        break
    a, b = b, r

_, (ba, bb) = vec
print(f"{N} * {ba} + {K} * {bb} == 1")
# => 9999991 * 3109 + 2236206 * -13903 == 1
x = bb * R % N
print(f"{K} * {x} mod {N} = {R}")
# => 2236206 * 5799546 mod 9999991 = 1234567
```




---
This page is auto-translated from [/nishio/剰余群での除算](https://scrapbox.io/nishio/剰余群での除算) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Collection of integer theory techniques"
---

[http://kirika-comp.hatenablog.com/entry/2018/03/12/210446](http://kirika-comp.hatenablog.com/entry/2018/03/12/210446) [pdf](https://github.com/kirika-comp/articles/releases/download/v1.0/seisuuron.pdf)
- 1 Basics: About the Algorithm 2
    - 1.1 Invariants in the Algorithm . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 2
- 2 Computation over mod p (modular arithmetic) 3
    - 2.1 Basics: Adding, Subtracting, and Multiplying Integers (Lv. 1) . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 3
    - 2.2 Basics: Inverses (Lv. 1) . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 3
    - 2.3 Basics: Adding, Subtracting, and Multiplying Fractions (Lv. 2) . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 4
- 3  [[binary progression]]  (Lv. 1) 5
    - 3.1 [[Finding monoidal structures and powers of two]] (Lv. 2) . . . . . . . . . . . . . . . . . . . . . . . . . . 6
    - 3.2  [[Good deformation avoids division by]]  (Lv. 2) . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 7
- 4  [[Strike with Abundance]]  (Lv. 2) 9
    - 4.1 Hit with [[Abundance of prime numbers]] (Lv. 2) . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 9
- 5 Algorithm for mod p 9
    - 5.1 Fundamentals . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 9
    - 5.2 mod sqrt,  [[Tonelli-Shanks algorithm]]  (Lv. 3) . . . . . . . . . . . . . . . . . . . . . . . . . 10
- 6 Group Theory (Lv. 4) 14
    - 6.1 Group (Lv. 4) . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 14
- 7 Mutual Laws of Square Surplus and Quadratic (Lv. 4) 15
    - 7.1  [[Lujandre symbol]]  . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 15
    - 7.2  [[law of reciprocity of square modulus]]  . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 16
    - 7.3  [[quadratic field]]  . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 16
    - 7.4  [[finite field]]  . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 17
    - 7.5  [[Frobenius mapping]]  . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 17
    - 7.6 Applications . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 17
- 8 Algorithm for mod p Part 2 18
    - 8.1 mod sqrt its 2, [[Lehmer's Algorithm]] (Lv. 3) . . . . . . . . . . . . . . . . . . . . . . . . . 18
    - 8.2 mod sqrt its 3, [[Cipolla's Algorithm]] (Lv. 4) . . . . . . . . . . . . . . . . . . . . . . . . . 21
- 9 Techniques for Using Polynomials (Lv. 4) 22
    - 9.1  [[Fast Fourier Transform]]  (FFT) (Lv. 3) . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 22
    - 9.2  [[Fermat's minor theorem]]  (Lv. 3) . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 24
    - 9.3  [[Special convolution using cyclic group structure]]  (Lv. 4) . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 29
    - 9.4  [[Convolution using 2^k squared roots mod p of 1]]  . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . 30
- 10  [[Pell equation]]  (Lv. 4) 31
- 11  [[monomial idealized range]]  (Lv. 5) 33
---
This page is auto-translated from [/nishio/整数論テクニック集](https://scrapbox.io/nishio/整数論テクニック集) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Power, inverse, factorial, factorial inverse, and combination in Python"
---

I was organizing the code I wrote for [[ABC171 F]] to reuse it, and while I was at it, I compared the speed with [maspy method](https://maspypy.com/numpyn-mod-p%e3%81%ae%e8%a8%88%e7%ae%97) and found that the maspy method compiled with [[Numba F]] and found that the one compiled with [[Numba]] was the fastest.

If the creation of a combinatorial table from 1,000,000 cases is a one-shot for a specific n, 35 msec; if the factorial and reciprocal factorial are created first and used around, 49 msec (30 msec for preparation).

I think my own work is saying 53msec, which is relatively good. Losing is losing.

Then, removing reshape and inversion from the MASPY method, we got 33 msec.
python

```
@numba.njit
def makeCombibationTableJointedNoReshapeNumba(N):
    """ make table of C(n, i) for i in [0, N)
    Jointed version of makeFactorialTableMaspy, 
    makeInvFactoTableMaspyOriginal, and makeCombibationTableMaspy.

    >>> list(makeCombibationTableJointedNumba(10000)[:5])
    [1, 10000, 49995000, 616668838, 709582588]

    %timeit makeCombibationTableJointedNoReshapeNumba(K)
    33 ms ± 809 µs per loop (mean ± std. dev. of 7 runs, 10 loops each)
    """
    K = math.ceil(math.sqrt(N + 1)) ** 2
    rootK = math.ceil(math.sqrt(K))

    facto = np.arange(K, dtype=np.int64)
    facto[0] = 1
    for i in range(1, rootK):
        facto[i::rootK] *= facto[i-1::rootK]
        facto[i::rootK] %= MOD
    for start in range(rootK, K, rootK):
        end = start + rootK
        facto[start:end] *= facto[start - 1]
        facto[start:end] %= MOD

    invf = np.arange(1, K + 1, dtype=np.int64)
    invf[-1] = getSingleInverseNumba(facto[K - 1])  # inverse of (k-1)!
    for pos in range(rootK - 2, -1, -1):
        invf[pos::rootK] *= invf[pos + 1::rootK]
        invf[pos::rootK] %= MOD

    for end in range(-rootK, -K, -rootK):
        start = end - rootK
        invf[start:end] *= invf[end]
        invf[start:end] %= MOD
    return facto[N] * invf[:N + 1] % MOD * invf[N::-1] % MOD
```



mounting
[https://github.com/nishio/atcoder/blob/master/memo/combination.py](https://github.com/nishio/atcoder/blob/master/memo/combination.py)
- Power: 13msec
- Inverse: 47msec
- Factorial: 13msec (K is excluded)
- InvFactorial: 17msec (Need to give (K - 1)!)
- Combination:
    - 35msec (if you need C(n, r) for specific n)
    - 19msec (need f and invf. 13 + 17 + 19 = 49msec)

memo
- Numba cannot reshape unless it is a contiguous array, so [np.ascontiguousarray
- The part where the inverse is obtained by [[Fermat's minor theorem]] is Numba-esque: "Float?" So I changed it to [[Euclid's reciprocal division]].
- I wonder if the maspy method is a kind of [[square partitioning]].
- In the original implementation, `[0, K)`
    - I think `[1, K]` would be better, since in many cases the problem condition says "including 10 ** 6".
    - I tried to implement it, but I thought it might be the source of the bug because n! is in n-1 in this case.
    - Better to make it one size larger.
        - A bit cumbersome because of the square number restriction.
        - I also included a code to make it one size larger.


[https://ikatakos.com/pot/programming_algorithm/number_theory/mod_combination](https://ikatakos.com/pot/programming_algorithm/number_theory/mod_combination)

---
This page is auto-translated from [/nishio/Pythonでの累乗・逆数・階乗・階乗逆数・組み合わせ](https://scrapbox.io/nishio/Pythonでの累乗・逆数・階乗・階乗逆数・組み合わせ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
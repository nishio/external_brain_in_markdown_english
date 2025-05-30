---
title: "ACL1B"
---

from [[ACL1]]
ACL1B
[B - Sum is Multiple](https://atcoder.jp/contests/acl1/tasks/acl1_b)
- ![image](https://gyazo.com/05e1340235546d99c96be1d91098fd5f/thumb/1000)
- Thoughts.
    - $1 + 2 + \cdots + k = k (k + 1) / 2$ so the problem condition is k * (k + 1) % N = 0
        - Note: mod 2N is correct
    - Explore and display naively for now, and find patterns.
    - k=N-1 when N is a prime number
    - k=N-1 even when N is a power of 2
    - It gets smaller when it's split into different prime factors.
    - Find the prime factorization f of N and get the maximum `m = max([p ** f[p] for p in f])`.
    - Consider the remainder r = N // m not satisfied by m
    - Find naively the smallest n such that nm + 1 or nm - 1 is a multiple of r
        - → This does not necessarily give the minimum solution required by the problem.
    - Ended up thinking the policy was no good.
- Official Explanation
    - A solution satisfying the above condition (and similar conditions) is obtained by [CRT
    - Do not calculate only for the largest m, but for the entire divisor
        - For some approximately m in N, as r = 2 * N // m
            - Is there a k such that k is a multiple of m, k+1 is a multiple of r, and so on?
                - In order to exist, m and r must be prime to each other
                - If they are prime to each other, it boils down to the existence of a solution to the [Chinese remainder theorem
            - [[irreducible enumeration]] is O(sqrtN) and CRT for each divisor is O(logN), so they can make it in time.
- [maspy's commentary:](https://maspypy.com/atcoder-参加感想-2020-09-20acl1)
    - CRT is not necessary.
    - $k \equiv 0 \pmod{m}, k \equiv -1 \pmod{r}$ when $k = am$.
        - $am \equiv -1 \pmod{r}$,
        - $ a \equiv -1 \cdot m^{-1} \pmod{r}$
        - So ` k = -1 * inv_mod(m, r) * m ` is fine, so
- CRT version
python

```
def solve(N):
    from math import gcd
    if N == 1:
        return 1
    ret = N - 1
    for n in all_divisor(2 * N, includeN=False):
        m = (2 * N) // n
        if gcd(m, n) != 1:
            continue
        k = crt(0, n, -1, m)
        if k < ret:
            ret = k
    return ret
```

- non-CRT version
python

```
def solve(N):
    if N == 1:
        return 1
    factors = factor(2 * N)
    num_factors = len(factors)
    if num_factors == 1:
        return N - 1
    factors = [p ** factors[p] for p in factors]
    ret = N - 1
    for i in range(2 ** num_factors - 1):
        prod = 1
        j = 0
        while i:
            if i & 1:
                prod *= factors[j]
            j += 1
            i >>= 1

        rest = (2 * N) // prod
        k = (-pow(prod, -1, rest) * prod) % (2 * N)
        if k < ret:
            ret = k

    return ret
```

    - Ummm [AC 21 TLE 21](https://atcoder.jp/contests/acl1/submissions/17258486)
        - Is the prime factorization slow or the re-bundling part slow?
            - I replaced it with [[Prime factorize by O(n^(1/4))]] and it came through [51msec](https://atcoder.jp/contests/acl1/submissions/17259156)
    - Also, pow asking for [[Inverse Element in mod P]] is a rather new feature since Python 3.8, so it didn't work in PyPy.
        - `ValueError: pow() 2nd argument cannot be negative when 3rd argument specified`
- 2N is the right story.
    - When N is 6, 1+2+3 = 6, so 3 is the solution
    - N would answer 2 because 2 * 3 mod 6 = 0 and 2 and 3 are prime to each other.
    - If 2N, then 2, 6 are not prime to each other, and 3, 4 3 is the correct answer.

---
This page is auto-translated from [/nishio/ACL1B](https://scrapbox.io/nishio/ACL1B) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
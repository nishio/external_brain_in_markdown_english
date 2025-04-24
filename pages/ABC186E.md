---
title: "ABC186E"
---

from [[ABC186]]
ABC186E
- ![image](https://gyazo.com/90585b907bd02b760801e90adbe4c60d/thumb/1000)
- [E - Throne](https://atcoder.jp/contests/abc186/tasks/abc186_e)
- In short, the problem is to find n such that [$ S + K n \equiv 0 \pmod{N}
    - Just do n = -S / K.
    - mod N, so the inverse original must be calculated for division
- We can find the [[Inverse Element in mod P]] of K
    - but the code I usually used that uses Fermat's minor theorem returns an incorrect value when P is not prime.
    - The inverse source of the 3 in the sample with mod 10 is exactly that. it would be 1.
    - Really 7: $3 \times 7 = 21 \equiv 1 \pmod{10}$
    - Find the inverse using [Extended Euclidean reciprocal division
- Again, K and P must be prime to each other, so gcd first and divide if not 1
    - No solution when S is not divisible
python

```
def solve(N, S, K):
    from math import gcd
    g = gcd(K, N)
    if g > 1:
        if S % g != 0:
            return -1
        N //= g
        K //= g
        S //= g

    invK = mod_inverse_ee(K, N)
    ret = (N - S) * invK % N

    return ret
[P is not prime mod P] 
```

- [https://twitter.com/drken1215/status/1340338865622564864?s=21](https://twitter.com/drken1215/status/1340338865622564864?s=21)
        - [[Chinese remainder theorem]]

---
This page is auto-translated from [/nishio/ABC186E](https://scrapbox.io/nishio/ABC186E) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
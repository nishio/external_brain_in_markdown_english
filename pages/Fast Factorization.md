---
title: "Fast Factorization"
---

    - Algorithm to slightly modify [[Eratosthenes' sieve]] to allow for [[prime factor decomposition]] without trial splitting
- Instead of having a true/false table of whether a number x is prime or not, make a table of the smallest prime number that divides x
python

```
def precompute(AS)
    maxAS = max(AS)
    eratree = [0] * (maxAS + 10)
    for p in range(2, maxAS + 1):
        if eratree[p]:
            continue
        # p is prime
        eratree[p] = p
        x = p * p
        while x <= maxAS:
            if not eratree[x]:
                eratree[x] = p
            x += p
    return eratree
```

- O(N log log N)
    - see [https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes](https://en.wikipedia.org/wiki/Sieve_of_Eratosthenes)
- `x = p * p`
    - Anything smaller than this, if it is a composite number, has an irreducible number smaller than p.
- When we actually do the prime factorization, we can just table subtract and divide until we get to 1.
    - High speed since this is log N
    - sqrt Faster than dividing by prime numbers less than or equal to N, but requires preprocessing, so it is suitable for many prime factorizations.
python

```
for a in AS:
    factors = []
    while a > 1:
        d = eratree[a]
        factors.append(d)
        a //= d
    ...
```


- By the way, to make it a "table of the smallest prime number that divides x", the loop is run up to N. If you want to make it "the smallest prime number or 0, and x is prime when 0", the loop can be run up to sqrt N.
    - Somewhat faster.
    - The prime factorization is where the case needs to be divided.

---
This page is auto-translated from [/nishio/高速素因数分解](https://scrapbox.io/nishio/高速素因数分解) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
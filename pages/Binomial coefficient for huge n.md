---
title: "Binomial coefficient for huge n"
---

If we want to find the binomial coefficient for a huge n(10^9), we will not be able to calculate n! in time because O(n)
$\binom{n}{k} = \frac{n!}{k!(n-k)!} = \frac{n!}{(n-k)!} \frac{1}{k!}$
and transforming each of them into O(k), we obtain

Mounting example
python

```
def naive_comb(n, k, MOD=MOD):
    assert n >= 0
    assert k >= 0
    if n < k:
        return 0
    k = min(k, n - k)
    a = 1
    b = 1
    for i in range(k):
        a *= (n - i)
        a %= MOD
        b *= (i + 1)
        b %= MOD
    return (a * mod_inverse(b, MOD)) % MOD
```

- For mod_inverse, see [[Inverse Element in mod P]].

- [[Combination about huge n]]
from  [[Combination in mod P]]

---
This page is auto-translated from [/nishio/巨大なnについての二項係数](https://scrapbox.io/nishio/巨大なnについての二項係数) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
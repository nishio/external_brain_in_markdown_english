---
title: "Derivation of the inverse modulo group asymptotic formula"
---

- In [[Division by the remainder group]], Euclid's reciprocal division is used to find the inverse, which takes O(log(N)) for each calculation.
In the case of creating [[inverse table]] all together, there is an incremental formula that can be created by O(1) for one and O(N) for all
- `inv[a] = MOD - inv[MOD % a] * (MOD / a) % MOD;`
python

```
for i in range(2, P):
    q, r = divmod(P, i)
    INV[i] = -INV[r] * q % P
```


d
Suppose the quotient of P divided by a is q and the remainder is r (`q, r = divmod(P, a)`)
- The following equation holds
- $P = aq + r$
- mod P for both sides
- $0 \equiv aq + r$
- Multiply by the inverse of a
- $0 \equiv q + a^{-1}r$
- transpose q
- $-q \equiv a^{-1}r$
- Multiply by the inverse of r
- $-qr^{-1} \equiv a^{-1}$
- The inverse of a could be obtained using the inverse of r smaller than a
- Just ask for the inverse yuan in order of decreasing size.

---
This page is auto-translated from [/nishio/剰余群逆元漸化式の導出](https://scrapbox.io/nishio/剰余群逆元漸化式の導出) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
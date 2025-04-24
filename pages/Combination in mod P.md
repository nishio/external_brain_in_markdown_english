---
title: "Combination in mod P"
---

Combination ( [[binomial coefficient]] )
$_nC_k = C(n, k) = \binom{n}{k} = \frac{n!}{k!(n-k)!}$
for large numbers n and k.

Assume that the value in mod P is good.
- Once that is obtained, the original value can be restored by [[Chinese remainder theorem]] from multiple values.

After taking the remainder, no ordinary division can be performed.
Then calculate and multiply [[Inverse Element in mod P]].
- For single-shot calculations, create an inverse original in logarithmic order.
- If you want to calculate a large number of calculations, you can create an [[inverse table]], and each calculation will be of constant order.
        - [[Derivation of the inverse modulo group asymptotic formula]]
    - [[binomial coefficient table]]

- [[Binomial coefficient for huge n]]

---
This page is auto-translated from [/nishio/mod Pでの組み合わせ](https://scrapbox.io/nishio/mod Pでの組み合わせ) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "lost communication"
---

Oblivious Transfer
Table pulling can be done with encryption.

Alice wants to do a table pull with m, but does not want to tell m to Bob who has table T.
- Bob should have a method that can compute Enc(m) → Enc(T(m))
- Of course Bob can't Enc(m)→m

[https://en.wikipedia.org/wiki/Oblivious_transfer](https://en.wikipedia.org/wiki/Oblivious_transfer)

If you want to send m, make m "a one-hot vector where only the mth is 1 and the rest are 0" and enc each element of the vector
- Enc(0) will of course have a different value

The table pull is the inner product of this one-hot vector.
If Enc is a quasi-isomorphic cipher, the inner product can be computed.

Ten years ago there were no quasi-isomorphic ciphers that could be multiplied.
A perfect quasi-isomorphic cipher was born.
That's computationally heavy, so "quasi-isomorphic ciphers that can be multiplied only once" were born.

What to do if you want to take a value from a 2D table
- In an additive-only quasi-homomorphic cipher, two indices are combined to form an index, like 256x+y.
    - Possible, but costly if the table is X * Y in size, since the message length is also X * Y
- Can be neatly done in a quasi-homomorphic cipher where multiplication can be done once.
    - If the product of two indices can be computed, because only where "both are 1" is there left a 1.


---
This page is auto-translated from [/nishio/紛失通信](https://scrapbox.io/nishio/紛失通信) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
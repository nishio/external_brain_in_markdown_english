---
title: "AES"
---

AES uses a set of 16 8-bit values as a basic block, but I had a misunderstanding about these 8-bit values until the other day, so here's a note

First, consider $F_2$. This is a set of two values, 0 and 1, which can be made into a ring by inserting XOR as addition and AND as multiplication.
The entire polynomial $K[F_2$] with this as a coefficient is itself a ring (proof required)
Dividing this ring by an irreducible polynomial and taking the remainder is also a ring (proof required)
At this time, AES divides by an 8-dimensional polynomial, so the remainder is of the form $a_0 x^7 + a_1 x^6 + ... + a_7 x^0$.
This 8-bit coefficient is the 8-bit value used in the AES basic block.

Addition between these 8-bit values is a bitwise XOR, but multiplication is not a bitwise AND.
Proof that addition is a bitwise XOR (proof required)

Proof that multiplication is not a bitwise AND (proof required)
- Suppose multiplication is AND.
- Multiplication of rings requires the existence of a unit source
- Given a unit source e, a * e = a for any a
- When a is 1111111111, this does not hold except e = 1111111111
- Existence of multiplicative inverse element
    - A body is a nontrivial unitary ring whose arbitrary nonzero source has a multiplicative inverse source."
        - Where did you come up with the idea that it's a body?
            - Multiplication must have an inverse source because of the need to perform the inverse operation during decoding
        - Just being a ring does not require the existence of a multiplicative inverse.
- For example, there is no multiplicative inverse because there is no source that ANDs to 11110000 to get 1111111111
- Therefore, multiplication is not AND.

Explanation of what multiplication ends up being (later)
- [https://en.wikipedia.org/wiki/Rijndael_MixColumns](https://en.wikipedia.org/wiki/Rijndael_MixColumns)

---
This page is auto-translated from [/nishio/AES](https://scrapbox.io/nishio/AES) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
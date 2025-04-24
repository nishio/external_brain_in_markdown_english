---
title: "abc152e"
---

[https://atcoder.jp/contests/abc152/tasks/abc152_e](https://atcoder.jp/contests/abc152/tasks/abc152_e)

- Thoughts.
    - AiBi is a common multiple of Ai, the same regardless of i
    - AiBi divided by Ai is Bi
    - So mathematically, the answer is to find the least common multiple, divide by each Ai, and multiply
    - There are 10^4 N values of 10^6 order A, so a naive calculation would be very difficult.
    - Least common multiple is all Ai multiplied by the greatest common divisor
    - Find the greatest common divisor first
        - This is only 10^4 times log(10^6) order of magnitude more than enough to calculate O(N log A)
    - Find [[Inverse Element in mod P]] to divide by the greatest common divisor
        - Since it is the inverse of a single number, it can be obtained in about log(mod).
    - Since division by Ai only cancels one of the products of all Ai [[obsolete rule prohibiting match-ups between wrestlers from the same group of stables]], and [[Cumulative product from left to right]].
        - Linear order preprocessing, this process is constant order
    - Add them together and you have the answer.
- Official Explanation
    - The considerations are the same up to the point of least common multiple.
    - Then trying to find the least common multiple with prime factorization
    - Prime factorization is on the order of the square root, 10^3, and we do it 10^4 times, so 10^7, in time.
    - Talk about O(A+NlogA) by speeding up the prime factorization through preprocessing.
            - [[Fast Factorization]], where the O(A) table is pre-built so that trial division is no longer necessary and prime factorization is of logarithmic order.
        - Is this as much of an order of magnitude as my solution after all this time?

---
This page is auto-translated from [/nishio/abc152e](https://scrapbox.io/nishio/abc152e) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
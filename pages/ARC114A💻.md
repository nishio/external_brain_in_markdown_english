---
title: "ARC114A💻"
---

from [[ARC114]]
ARC114A💻
- Thoughts.
    - Choose some of the 20 or so prime numbers and cover the whole thing.
    - Of the methods, the one with the lowest cost
    - There are 50 objects to be covered, and having "what is covered" in bits is a bit too much at 2^50.
    - Minimum cut?
    - If the cost is the product of each option → logarithm, it is the sum.
    - Cost minimization is minimum cut
    - I thought I'd implement it and see...
        - I don't know how to express "either prime factor 2 or prime factor 5 must be S" when there are 10
    - AC by the greedy method of taking prime numbers, which are the divisors of many numbers, in order.
        - This is a false solution
        - I would choose 2 for 3,5,7,6,10,14 or something like that, but it's right not to.
    - Since there are 15 prime numbers, we can afford to do a full search of 2^15=32768 cases
- > A problem is the same as [[ABC195F💻]], just check every prime number it should [tw](https://twitter.com/kyopro_friends/status/1371104057004150784)

---
This page is auto-translated from [/nishio/ARC114A💻](https://scrapbox.io/nishio/ARC114A💻) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
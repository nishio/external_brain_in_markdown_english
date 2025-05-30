---
title: "ABC164D"
---

[D - Multiple of 2019](https://atcoder.jp/contests/abc164/tasks/abc164_d)
- ![image](https://gyazo.com/badbc878097ba5f4df01c2d1902b3b13/thumb/1000)
- Thoughts.
    - If the remainder of the range from i to j is known, then multiply by 10, add one digit, and take the remainder in constant time
    - But if we wait for too much for each starting point, the total is of the order of squares.
    - So we can set this to [[frequency table]] of a constant width
        - PS, it is indeed a constant, but it's 2019 x 200000, so it's going to TLE.
            - [[Estimating computational quantities]] Miss.
        - [[unAC]]
- Official Explanation
    - A slightly different approach
    - It's similar to doing operations on a range with cumulative sums and inverse operations.
        - I thought about it a little when I was considering it per se, but I mistakenly thought it was a no-no.
        - ![image](https://gyazo.com/2bd8c05b48f05f4532c7434dc0a00e7b/thumb/1000)
        - $x \equiv A_j - A_i \times 10^{j-i} \pmod{2019}$
            - Quickly assume that the power of 10 part is in the way and cannot be used.
        - Cumulative from the left, not from the right
            - That's more natural since it's a number of digits, not a sequence of numbers.
            - ![image](https://gyazo.com/1add8c37dc897eb81d632cfb85af2d94/thumb/1000)
            - $x \times 10^{i-j} \equiv B_i - B_j  \pmod{2019}$

            - I'm only interested in whether the remainder of x is zero in this problem.
            - Multiplication by powers of 10 can be ignored because 10 is prime to 2019.
    - From left to right: Accumulation → [[Frequency → Triangular number]].

---
This page is auto-translated from [/nishio/ABC164D](https://scrapbox.io/nishio/ABC164D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
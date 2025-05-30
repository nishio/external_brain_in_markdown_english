---
title: "ARC110D"
---

![image](https://gyazo.com/829c06c94c53cc49c05c234e5f3445c5/thumb/1000)
[D - Binomial Coefficient is Fun](https://atcoder.jp/contests/arc110/tasks/arc110_d)
- Thoughts.
    - With N=2000, O(N^2) would be fine.
    - With M=10^9, it seems impossible to do dynamic programming like "the first one is x and the rest are M-x".
        - Viewing [[field hockey stick identity]] -> Looks different
    - If B is smaller than A, it is zero and can be ignored.
    - Distribute the remaining $R = M - \sum A_i$ among 2000 boxes
    - Since there are about $\binom{2000 + R}{R}$ of individual events, they cannot be calculated individually and added together in time.
        - → should be able to be bundled and calculated by some formula transformation.
        - View [binomial coefficient formula
        - [[Vandermonde's identity]]
    - $\sum_{i=0}^k \binom{n}{i}\binom{m}{k - i} = \binom{n+m}{k}$
        - It's a product of binomial coefficients into a single binomial coefficient, which is close to the objective.
        - Adding a lower value is also close to the objective of being constant
        - Cannot be used directly because the value above changes.
        - There must be a formula like a variant of this -> let's find it.
    - Write a code to naively calculate $f(A,B,K) = \sum_i \binom{A + i}{i}\binom{B + K - i}{K - i}$ that you want to get and observe
:
| 1 | 1 | 1 | 4 | 4C1 |
| -- | -- | -- | -- | -- |
| 1 | 1 | 2 | 10 | 5C2 |
| 1 | 1 | 3 | 20 | 6C3 |
        - →$f(A,B,K) = \binom{A + B + K + 1}{K}$
    - In the case of Section 3.
        - $\sum_{ij} \binom{A_1 + i}{i} \binom{A_2 + j}{j} \binom{A_3 + (R - i - j))}{R - i - j}$
        - $= \sum_{i+j} \binom{A_1 + A_2 + (i+j) + 1 }{i+j} \binom{A_3 + (R - (i + j)))}{R - (i + j)}$
        - $= \sum_{k} \binom{A_1 + A_2 + k + 1 }{k} \binom{A_3 + (R - k))}{R - k}$
        - $= \binom{A_1 + A_2 + 1 + A_3 + R + 1}{R}$
    - generally
    - $\sum A_i + (N - 1) (1 + R)$
        - This is a mistake see addendum A
    - Calculating sample 1 with this formula gave 8, but I doubt it because of the messy calculations along the way.
        - I'm supposed to have to come up with all the patterns below R, and I'm using the formula R=1.
    - In the first place, R can be about 10^9, so it seems impossible to calculate the binomial coefficient?
        - This is a mistake see addendum B

- Official Explanation
    - $S = \sum A_i$ as $\binom{N+M}{S+N}$ is the answer
    - Since R=M-S $\binom{N+M}{S+N} = \binom{N+M}{N+M-R} = \binom{N+M}{R}$
    - Why does this happen?
        - The official explanation in natural language is, in essence, the following formula
        - $\sum_i \binom{i}{A}\binom{N-i-1}{B} = \binom{N}{A+B+1}$

    - Postscript B
        - Calculation of binomial coefficients
        - I tend to do "create a binomial coefficient table for faster calculation".
            - I made a library...
        - But when the upper binomial coefficient is 10^9 and the lower is 10^6, as in this case, we should have used $C(n,m) = P(n,m) (m!)^{-1}$.
            - This calculation can be done for O(m), so
            - Faster than creating a table of size n
                - [[Binomial coefficient for huge n]]

    - Postscript A
        - generally
        - $\sum A_i + (N - 1) (1 + R)$
            - This is an error.
        - $X= \sum A_i + (N - 1) + R$ is correct
            - $R = M - \sum A_i$ so $X = M + N - 1$
                - Oh, that one doesn't fit...
        - This formula only calculates the case where the "value to be assigned" is exactly R
        - The value we want is $\sum_{r=0}^R \binom{S + N + r - 1}{r}$
                - Use [[field hockey stick identity]].
            - $\sum_{i=0}^k \binom{n+i}{i} = \binom{n+k+1}{k}$
        - This increases by 1, and the value we seek is $\binom{S + N + R }{R}$.
        - $\binom{S + N + R }{R} = \binom{S + N + R }{S + N} = \binom{N + M}{S + N}$
        - Now we come down to the same formula as in the official explanation.
- → Explanation AC

    - [[formal power series]] and can be solved by attributing to
    - [[ARC110D_FPS]]

- [[OEIS]]
    - [https://twitter.com/yuruhiya/status/1335222719160315904?s=21](https://twitter.com/yuruhiya/status/1335222719160315904?s=21)
    - This time I was judging it by the naked eye, but when I was done, I used OEIS and it was a breeze, so I'll do that next time.

- A path that does not involve "predicting general terms from experimentally constructed sequences."
        - I could transform the equation by interpreting it as [[Collapsing Duplicate Combinations]].
    - Sort by: [[ARC110D_nonFPS]].

from [[ARC110]]

---
This page is auto-translated from [/nishio/ARC110D](https://scrapbox.io/nishio/ARC110D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "ARC110D nonFPS"
---

Solution of [[ARC110D]] without formal power series

![image](https://gyazo.com/829c06c94c53cc49c05c234e5f3445c5/thumb/1000)
[D - Binomial Coefficient is Fun](https://atcoder.jp/contests/arc110/tasks/arc110_d)
- When Bi is less than Ai, the binomial coefficient is zero
- So there is no need to consider cases where Bi is small.
- $B_i = A_i + D_i$. $D_i \ge 0$
- $S := \sum A_i$ and the rest as [$ R:= M - S
- $\sum D_i \le R$.
- It takes the form of "distribute R (or less) balls in N frames."
- Consider distributing just K balls in 2 frames for simplicity
- (0, K), (1, K-1), ... , (K, 0), there is a way to distribute
- The solution X2 we want is $X_2 = \sum_{i=0}^K \binom{A_1 + i}{A_1}\binom{A_2 + K - i}{A_2}$
- There is a way to implement this naively and obtain it for some values and predict the answer formula from them (I did so), but in this page, I will do it by transforming the formula.
- From the symmetry of the binomial coefficients $\binom{A_1 + i}{A_1} = \binom{A_1 + i}{i}$
- $X_2 = \sum_{i=0}^K \binom{A_1 + i}{i}\binom{A_2 + K - i}{K - i}$
    - [[nested combination]] : number of ways to select k out of n, allowing for duplication
    - $H^n_k = \binom{n + k - 1}{k}$
- Write in the form of duplicate combinations:.
    - $X_2 = \sum_{i=0}^K H^{A_1+1}_i H^{A_2+1}_{K-i}$
- Duplicate combinations of A1+1 to i and A2+1 to K-i contents of sigma to choose from
- Adding up for all possible i's results in K duplicate combinations to choose from A1+A2+2.
    - $X_2 = H^{A_1+A_2+2}_K$
- Return to binomial coefficient form
    - $X_2 = \binom{A_1 + A_2 + K + 1}{K}$
- So far, the answer for distributing exactly K with N=2 can be expressed in terms of a single binomial coefficient
- Next, consider N over 3.
    - Rename variable K to i
        - $X_2 = \binom{A_1 + A_2 + i + 1}{i}$
    - At this point, X at N=3 becomes
        - $X_3 = \sum_i \binom{A_1 + A_2 + i + 1}{i} \binom{A_3 + K - i}{K - i}$
    - This is just A1 becoming A1+A2+1, so the argument above can be used as is.
        - $X_3 = \binom{A_1 + A_2 + 1 + A_3 + K + 1}{K} = \binom{A_1 + A_2 + A_3 + K + 3 - 1}{K}$
- At general N:.
    - $X_N = \binom{S + K + N - 1}{K}$
    - This was just the solution when they were handing out K pieces.
    - The answer X that the problem is asking for is the sum of everything below R
        - $X = \sum_{K=0}^R \binom{S + K + N - 1}{K}$
    - [[Field hockey stick identity]] :
    - $\sum_{i=0}^k \binom{n+i}{i} = \binom{n+k+1}{k}$
- Field hockey stick identity to find the sum
    - $X = \sum_{K=0}^R \binom{S + K + N - 1}{K} = \sum_{K=0}^R \binom{S + N - 1 + K}{K} = \binom{S + N - 1 + R + 1}{R} = \binom{S + N + R}{R}$
- From the symmetry of the binomial coefficients
    - $X = \binom{S + N + R}{R} = \binom{S + N + R}{S + N}$
- $R:= M - S$, so
    - $X = \binom{S + N + R}{S + N} = \binom{N + M}{S + N}$
- Now the values to be sought are combined into a single binomial coefficient.
- N+M will be about 10^9, but S+N will not be 10^7, so if properly implemented, it will be in time.
        - [[Binomial coefficient for huge n]]
---
This page is auto-translated from [/nishio/ARC110D nonFPS](https://scrapbox.io/nishio/ARC110D nonFPS) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
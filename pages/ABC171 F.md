---
title: "ABC171 F"
---

![image](https://gyazo.com/06a507356d75cd4cd98f157068093c3d/thumb/1000)
The problem is to count the possible strings that can be made by inserting an English lowercase letter up to 1 million times in any location in a string of up to 1 million English lowercase letters of any length. [Problem statement](https://atcoder.jp/contests/abc171/tasks/abc171_f)

Thoughts during the contest
- 45 minutes remaining
    - It would be DP after looking into the short string case and finding the regularity.
    - ![image](https://gyazo.com/92443e90484b35f57d2fbea9be5d2738/thumb/1000)![image](https://gyazo.com/b066f25b6d83ddb4a44edd7876bf69c4/thumb/1000)![image](https://gyazo.com/1a303ec1a5234133a2fcf237b87103c3/thumb/1000)
    - Okay, regardless of the content of the specific string, if we add one character to a string of character type K with length N, the following relationship holds!
        - f(N+1, K+1) = (26 - K) * (N + 1) * f(N, K)
        - f(N+1, K) = ((K - 1) * (N + 1) + 1) * f(N, K)
    - DP specification
        - A confluence is about to happen.
        - Arrange the squares in a square and fill them in, starting from the corner...
        - Hey, isn't this a 1,000,000 x 1,000,000 order?
- At this point, 15 minutes left.
    - Let the program actually enumerate and count all the patterns for a short string, and time runs out while you're trying to discover the pattern.

After the contest after reading the commentary
- ![image](https://gyazo.com/be0eaeaa0e90dfe8e3bdf686981650c9/thumb/1000)
    - 25 times considering inserting a character at the beginning of the string.
        - Inserting the same as the first character should not count because it is indistinguishable from inserting the second character.
        - Therefore, 26 characters minus one character, 25.
    - No further preceding text should be inserted after this insertion.
        - Because it's indistinguishable from one in which the order of insertion is swapped.
        - In general, the inserted characters are identical with the timing of the inserted characters swapped, so it must be a combination, not a permutation
        - Since there are duplicates, combinations with replacements (I forget what it is called in Japanese) are used.
- ![image](https://gyazo.com/36611c3416e86632e0db04d9961c5019/thumb/1000)
    - When the cursor position is N and the number of characters to be added is K, the goal is reached when the cursor reaches 0,0 after repeating the two choices of adding or moving the cursor forward.
    - If you look closely, you can see that the road is 25 times as long as any other road along the way, so it would be a good idea to split the case when you enter the 26 times road in the lower right corner.
- ![image](https://gyazo.com/4e7c83ae3b8aa3aa16ce4c2a044b885c/thumb/1000)
    - One way to get into the 26x path from the beginning.
    - N-1 street to enter from after taking one 25.
        - Two ways in the figure
        - (And I thought at this point, but there are N+1 insertion points for a string of length N, so there are really N ways, foreshadowing A)
    - Taking 2 25 is a combination of choosing 2 with duplicates
        - Three ways in the figure
    - So the value we are looking for is
        - $\sum_{i=0}^K 25^i 26^{K-i} C^R(N-1, i)$
- I'll do the calculations right away, but the answer for sample 1 doesn't match.
    - I tried shifting N and K by one and found that when I increased N by one, it turned out to be correct, so I decided to go with that (hey, hey!).
        - $\sum_{i=0}^K 25^i 26^{K-i} C^R(N, i)$
    - I found out why when I was writing this commentary, so the result is okay, foreshadowing A recovery.

Code that correctly answers Sample 1
python

```
K = 5
S = "oof"
P = 10 ** 9 + 7
N = len(S)


def factorial(n):
    ret = 1
    for i in range(2, n + 1):
        ret *= i
    return ret


def comb_rep(n, r):
    return factorial(n + r - 1) // factorial(r) // factorial(n - 1)


ret = 0
for i in range(K + 1):
    ret += (
        (25 ** i) *
        (26 ** (K - i)) *
        comb_rep(N, i)
    )
print(ret)
```


- I tried entering sample 2 as is and it takes a long time.
    - Of course, you're probably doing long-integer operations with very large digits, since you're not taking the remainder.
    - Let's write the three values on the right in a table while taking the remainder and reuse them $25^x, 26^x, x!$.
- Sample 2 now calculates fast enough, but for some reason the answer is different...
    - It's permissible to take the remainder and then add, subtract, and multiply, but not the integer division you're doing in the combination.
    - [Computation of the remainder of a binomial coefficient (nCk) divided by a prime number (p) commonly used in competitive pro and a summary of the inverse element | Algorithm Logic](https://algo-logic.info/combination/)
        - I see, so if we find the inverse element, we can divide by multiplication.
    - [How to find binomial coefficient (nCk mod. p) and inverse (a^-1 mod. p) often - Kenchon's record of competitive professional devotion](https://drken1215.hatenablog.com/entry/2018/06/08/210000)
        - `inv[a] = MOD - inv[MOD % a] * (MOD / i) % MOD;`
        - Using this formula, the inverse can be obtained with O(1), and the inverse table can be created with O(N).
        - The derivation of the asymptotic equation is not properly thought out.
            - Added: [[Derivation of the inverse modulo group asymptotic formula]].
        - At any rate, by using this, I got sample 2 right.
python

```
    f = 1
    invf = 1
    for i in range(2, N + K):
        f *= i
        f %= P
        F[i] = f
        q, r = divmod(P, i)
        INV[i] = -INV[r] * q % P
        invf *= INV[i]
        invf %= P
        INVF[i] = invf
```


- I tried submitting it and it was a TLE.
    - Compiled by [[numba]] that it would work well because it's a bunch of numerical calculations.
    - AC [https://atcoder.jp/contests/abc171/submissions/14596326](https://atcoder.jp/contests/abc171/submissions/14596326)

- Speed comparison at hand
:

```
pure python
real    0m2.910s
user    0m2.781s
sys     0m0.124s

compiled with numba
real    0m0.363s
user    0m0.683s
sys     0m0.139s
```

I measured how much faster it is with numba, but user is beyond REAL... does that mean that Python code that doesn't think about anything is running multi-threaded (GIL OFF)?

#atcoder #ABC171
---
This page is auto-translated from [/nishio/ABC171 F](https://scrapbox.io/nishio/ABC171 F) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
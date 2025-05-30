---
title: "DP S"
---

[S - Digit Sum](https://atcoder.jp/contests/dp/tasks/dp_s)
- The question of how many natural numbers less than or equal to some number K satisfy the condition
    - Assumption that it is not possible to naively check K numbers because K is too big.
        - [[Digit DP]]
    - > Digit DPs are much easier to write than DPs to receive.
        - [EDPC Commentary M-T - kyopro_friends' diary](https://kyopro-friends.hatenablog.com/entry/2019/01/12/231035)
        - I see, when I tried it before and bugged it, I was doing it with the implementation I was getting.
- First, consider a simple "count up the number of natural numbers less than or equal to K" with DP
    - ![image](https://gyazo.com/c9063ac33df020121c1f8d9ce839578a/thumb/1000)
    - Counting the number of natural numbers less than or equal to 57
        - Includes zeros, so "57 less than 57 and 1 equal".
    - The first i digits are the domain, and the number of "numbers less than or equal to K" and "numbers equal to K" up to that point are the DP values.
        - By the way, the "number that is equal k" is always 1, so there's no need to have it in a table.
        - I'm wondering if there are a lot of explanations, etc., that have it in a table, and sometimes that's more convenient to implement if it's a more complex problem.
        - In this issue, I counted every so much divided by D to check for the additional condition "divisible by D", but in my implementation, I did not provide a table for "equal K".

python

```
def solve(N, D):
    less = [0] * D
    equal = 0
    for digit in N:
        new_less = [0] * D
        for new_digit in range(10):
            for d in range(D):
                new_less[(d + new_digit) % D] += less[d]
            if new_digit < digit:
                new_less[(equal + new_digit) % D] += 1
        for d in range(D):
            new_less[d] %= MOD
        less = new_less
        equal += digit
        equal %= D

    ret = less[0]
    ret -= 1  # for x = 0
    if equal == 0:  # for x = N
        ret += 1
    return ret % MOD
```



old version
python

```
def solve(K, D):
    K = [x - ord("0") for x in K]
    N = len(K)
    less = [[0] * D for i in range(N + 1)]
    border = 0
    for i in range(N):
        for j in range(10):
            for d in range(D):
                less[i][(d + j) % D] += less[i - 1][d]
                less[i][(d + j) % D] %= MOD
            if j < K[i]:
                less[i][(border + j) % D] += 1
        border += K[i]
        border %= D

    ret = less[N - 1][0] - 1
    ret += (border == 0)
    return ret % MOD
```


[https://atcoder.jp/contests/dp/submissions/15082801](https://atcoder.jp/contests/dp/submissions/15082801)

---
This page is auto-translated from [/nishio/DP S](https://scrapbox.io/nishio/DP S) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
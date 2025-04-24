---
title: "DP O"
---

[O - Matching](https://atcoder.jp/contests/dp/tasks/dp_o)
- The problem of counting up a permutation of 21 things that satisfy certain conditions
- There are 21 different "usable ones" when deciding on one top and considering the remaining 20 permutations.
    - Therefore, "usable things" is the domain of definition, and the number of things that satisfy the condition is the value.
    - The "usable ones" are a subset of a set of at most 21, so 2^21, or approximately 10^7
    - Enumerating subsets of a small set is fast using bitwise operations (not so much in raw Python).
    - I guess some people call it [[bitDP]].
- Raw Python was going to TLE, but with PyPy, AC
python

```
def solve(N, data):
    FULLBIT = (1 << N) - 1
    memo = [-1] * (1 << N)

    def f(cursor, available):
        if cursor == N:
            return 1
        ret = memo[available]
        if ret != -1:
            return ret
        ret = 0
        j = 0
        m = available
        while m:
            if m & 1:
                # available woman
                if data[cursor * N + j]:
                    # acceptable
                    ret += f(cursor + 1, available ^ (1 << j))
            j += 1
            m //= 2
        ret %= MOD
        memo[available] = ret
        return ret

    return f(0, FULLBIT)
```

[https://atcoder.jp/contests/dp/submissions/15068618](https://atcoder.jp/contests/dp/submissions/15068618)

---
This page is auto-translated from [/nishio/DP O](https://scrapbox.io/nishio/DP O) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
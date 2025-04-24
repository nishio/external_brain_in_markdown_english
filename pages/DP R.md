---
title: "DP R"
---

[R - Walk](https://atcoder.jp/contests/dp/tasks/dp_r)
- The problem of counting up paths of length K in a directed graph
- DP, which in a naive way finds the number of paths of length k from the number of paths of length k-1.
- But the problem condition that K is at most 10^18 makes the method of doing K iterations impossible.
- The world leaps to "product of matrices" and "[[iterative square law]]" at this point, but I'll break it down a bit more.
- What to do when the same process needs to be done N times but O(N) is too slow?
    - It would be good to log N in a binary tree-like way, right?
    - If the process for N can be done quickly using the result of the process for N/2, then log N is obtained.
- This just happens to be a matrix multiplication in this case.

- This is what happens when you write in a simple way
    - This is WA
    - The reason is that multiplication of a matrix of size 50 with elements up to 10^9 exceeds the 64-bit range of elements.
        - It's too late to mod after multiplying.
python

```
def solve(N, K, X):
    powK = np.eye(N, dtype=np.int64)
    while K:
        if K & 1:
            powK = powK.dot(X)
            powK %= MOD
        X = X.dot(X)
        X %= MOD
        K //= 2
    return powK.sum() % MOD
```


- It's still 60 bits to the point where the elements are multiplied together, so take the mod there and then add them together.
python

```
def solve(N, K, X):
    def modmul(x, y):
        ret = np.zeros(x.shape, np.int64)
        for i in range(N):
            for j in range(N):
                v = x[i, :] * y[:, j]
                v %= MOD
                ret[i, j] = v.sum() % MOD
        return ret

    powK = np.eye(N, dtype=np.int64)
    while K:
        if K & 1:
            powK = modmul(powK, X)
        X = modmul(X, X)
        K //= 2
    return powK.sum() % MOD
```


[https://atcoder.jp/contests/dp/submissions/15081435](https://atcoder.jp/contests/dp/submissions/15081435)

---
This page is auto-translated from [/nishio/DP R](https://scrapbox.io/nishio/DP R) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
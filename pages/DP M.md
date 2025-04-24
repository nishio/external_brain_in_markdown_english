---
title: "DP M"
---

[M - Candies](https://atcoder.jp/contests/dp/tasks/dp_m)
![image](https://gyazo.com/7f00d3569b97262049eab2547f73d1ad/thumb/1000)

- Distribution Counting Issues
- Heavy addition at DP confluence.
        - [[cumulative sum]] is obtained in advance.

Rustic solution, this will pass all samples except the last.
python

```
def solve(N, K, XS):
    table = [0] * (K + 1)
    for i in range(XS[0] + 1):
        table[i] = 1

    for i in range(1, N):
        v = 0
        newtable = [0] * (K + 1)
        for j in range(K + 1):
            v = 0
            for k in range(XS[i] + 1):
                if j - k < 0:
                    break
                v += table[j - k]
                v %= MOD

            newtable[j] = v
        table = newtable

    return table[K]
```


What's wrong with simple is the addition loop, so find the cumulative sum in advance.
python

```
def solve(N, K, XS):
    table = [0] * (K + 1)
    for i in range(XS[0] + 1):
        table[i] = 1

    for i in range(1, N):
        v = 0
        newtable = [0] * (K + 1)
        accum = [0] * (K + 1)
        acc = 0
        for j in range(K + 1):
            acc += table[j]
            accum[j] = acc

        for j in range(K + 1):
            v = accum[j]
            k = j - XS[i] - 1
            if k >= 0:
                v -= accum[k]

            newtable[j] = v % MOD
        table = newtable

    return table[K]
```



---
This page is auto-translated from [/nishio/DP M](https://scrapbox.io/nishio/DP M) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
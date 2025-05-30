---
title: "DP N"
---

[N - Slimes](https://atcoder.jp/contests/dp/tasks/dp_n)
- Attach adjacent objects
- Cost varies depending on the order of attachment.
- Cost minimization issues
- DP that defines a region as a domain.
    - Same as [DP L
    - DP as the value of the lowest cost to attach the area when the area is specified.
    - [[cumulative sum]]
python

```
def solve(N, XS):
    accum = list(accumulate(XS)) + [0]
    @lru_cache(maxsize=None)
    def sub(L, R):
        if L == R:
            return 0
        ret = INF
        for x in range(L, R):
            v = sub(L, x) + sub(x + 1, R)
            if v < ret:
                ret = v
        return ret + accum[R] - accum[L - 1]
    return sub(0, N - 1)
```


Cython
python

```
cdef long long[400 * 400] table
cdef long long[410] accum

cdef sub(long L, long R):
    cdef long long ret
    if L == R:
        return 0
    ret = table[L * 400 + R]
    if ret != 0:
        return ret

    ret = INF
    for x in range(L, R):
        v = sub(L, x) + sub(x + 1, R)
        if v < ret:
            ret = v
    ret += accum[R + 1] - accum[L]
    table[L * 400 + R] = ret
    return ret

cdef solve(N, XS):
    cdef long i
    cdef long long v
    v = 0
    accum[0] = 0
    for i in range(N):
        v += XS[i]
        accum[i + 1] = v
    return sub(0, N - 1)
```

[https://atcoder.jp/contests/dp/submissions/15066323](https://atcoder.jp/contests/dp/submissions/15066323)

---
This page is auto-translated from [/nishio/DP N](https://scrapbox.io/nishio/DP N) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
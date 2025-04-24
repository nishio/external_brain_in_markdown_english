---
title: "abc130_d"
---

[D - Enough Array](https://atcoder.jp/contests/abc130/tasks/abc130_d)
- Given a sequence of numbers, count up the contiguous subsections of the sequence whose sum is greater than or equal to K
- Sequence up to 10^5
- First, a simple one (although [[cumulative sum]] can be written in a more simple way since it has been used...)
python

```
def solve(N, K, XS):
    from itertools import accumulate
    acc = [0] + list(accumulate(XS))
    ret = 0
    for i in range(N):
        for j in range(i + 1, N + 1):
            if acc[j] - acc[i] >= K:
                ret += 1
    return ret
```


And this is 10^10 in the order of squares, so change one of them to log N
- [[bisect]]
python

```
def solve(N, K, XS):
    import bisect
    from itertools import accumulate
    acc = [0] + list(accumulate(XS))
    ret = 0
    for i in range(N):
        lb = acc[i] + K
        j = bisect.bisect_left(acc, lb)
        ret += N + 1 - j
    return ret
```

AC [submitted #15126807 - AtCoder Beginner Contest 130](https://atcoder.jp/contests/abc130/submissions/15126807)

---
This page is auto-translated from [/nishio/abc130_d](https://scrapbox.io/nishio/abc130_d) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
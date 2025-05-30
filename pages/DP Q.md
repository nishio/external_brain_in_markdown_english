---
title: "DP Q"
---

[Q - Flowers](https://atcoder.jp/contests/dp/tasks/dp_q)
- Given two sequences of numbers, the problem of choosing the one that maximizes the sum of the given scores in the other sequence among all the subsequences that would be a monotonically increasing sequence of one of the sequences.

- As for the small sample problem, this will solve it.
    - If this max part is naively O(N), the whole thing would be N^2, which is 10^10, so it won't make it.
    - So use an algorithm that can compute max in log N
            - [[Fennic tree]]
python

```
def solve(N, HS, VS):
    values = [0] * (N + 1)
    for i in range(N):
        h = HS[i]
        values[h] = max(values[:h]) + VS[i]

    return max(values)
```


Fennic tree
python

```
def solve(N, HS, VS):
    bit = [0] * (N + 1)  # 1-origin

    def bit_put(pos, val):
        assert pos > 0
        x = pos
        while x <= N:
            bit[x] = max(bit[x], val)
            x += x & -x  # (x & -x) = rightmost 1 = block width

    def bit_max(pos):
        assert pos > 0
        ret = 0
        x = pos
        while x > 0:
            ret = max(ret, bit[x])
            x -= x & -x
        return ret

    for i in range(N):
        h = HS[i]
        m = bit_max(h)
        bit_put(h, m + VS[i])

    return bit_max(N)
```

AC [https://atcoder.jp/contests/dp/submissions/15080447](https://atcoder.jp/contests/dp/submissions/15080447)

---
This page is auto-translated from [/nishio/DP Q](https://scrapbox.io/nishio/DP Q) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
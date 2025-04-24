---
title: "ABC179D"
---

![image](https://gyazo.com/7b170df6b0f48886ab9a41790797f20e/thumb/1000)

[D - Leaping Tak](https://atcoder.jp/contests/abc179/tasks/abc179_d)
- ![image](https://gyazo.com/39b5c5d2890f126f81169312eb00f3b3/thumb/1000)
- After worrying for a while, skip to E.
    - Worries, "What, you don't want this to be too broad in scope?" ← correct
- I wrote it in a naive memoized recursive DP and sure enough [TLE](https://atcoder.jp/contests/abc179/submissions/16881501)
- Even with a DP that fills in a loop from the smallest to the largest [TLE](https://atcoder.jp/contests/abc179/submissions/16882554)
- But when you look at that code, you realize, "Oh, in essence, we just need to destroy this innermost loop.
        - [AC](https://atcoder.jp/contests/abc179/submissions/16885434) in [[cumulative sum]]
- A few cleaned up codes.
python

```
def solve(N, K, SS):
    count = [0] * (N + 10)
    count[0] = 1
    accum = [0] * (N + 10)
    accum[0] = 1

    for pos in range(1, N):
        ret = 0
        for left, right in SS:
            start = pos - right - 1
            end = pos - left
            ret += (accum[end] - accum[start])
            ret %= MOD
        count[pos] = ret
        accum[pos] = accum[pos - 1] + ret

    ret = count[N - 1]
    return ret % MOD
```

- I saw someone on Twitter saying that it was the "Imosu Act (fifth highest of the eight hereditary titles, later demoted to sixth highest of eight)", but I don't think so. I was not aware of that.
    - The problem that needs to be solved is that the part of the DP calculation that calculates the sum of a range is slow because it "adds up to a lot of numbers" when the range is large.
    - So, we create a separate array of "sums of numbers calculated so far".
        - This can be made by "adding the new value to the previous value".
        - They call this [[cumulative sum]].
    - Whenever a sum over a wide range is needed, it can be obtained by subtracting the cumulative sum before one of the range start points from the cumulative sum at the range end point.
    - ![image](https://gyazo.com/7b170df6b0f48886ab9a41790797f20e/thumb/1000)
- Some people on Twitter are saying it's [[segment tree]].
    - Segment trees are faster than O(N), which computes the sum by looping, because the range sum is O(logN).
        - The cumulative sum used in this case is O(1), which is even faster
    - While cumulative sums can only contain values from the beginning, segment trees can contain values at any position. This flexibility is the only reason for the slowness.
    - In this case, since the DP was made from the beginning, there was no need to put it in an arbitrary position.

[[ABC179]]

---
This page is auto-translated from [/nishio/ABC179D](https://scrapbox.io/nishio/ABC179D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
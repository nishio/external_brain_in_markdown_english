---
title: "ABC169 F"
---

Given a sequence A of numbers of size 3000. For all its subsequences T, the problem is to count up the number of such subsequences of T whose elements sum to a given S. [Problem](https://atcoder.jp/contests/abc169/tasks/abc169_f)

Thinking about all subsets is impossible, of course, since it is 3000 power of 2. Think in DP for small sample data, 2,2,4 and S=4.
![image](https://gyazo.com/6d14a1c740a68c6be7f9b2814efabf15/thumb/1000)
There are two paths, one where 2,2 makes 4 and one where 4 makes 1. Consider how the thickness of each pathway is determined.
![image](https://gyazo.com/3a85007b49caba15b0f55fc8d63688f0/thumb/1000)
Make it plainly a code.
python

```
import numpy as np
P = 998244353

# N = 10
# S = 10
# AS = list(map(int, "3 1 4 1 5 9 2 6 5 3".split()))
N, S = map(int, input().split())
AS = list(map(int, input().split()))
DP = np.zeros((S + 1, N + 1), dtype=np.int64)
DP[0, 0] = 1
# print(DP)

for i in range(N):
    for j in range(S + 1):
        v = DP[j, i] * 2
        if AS[i] <= j:
            v += DP[j - AS[i], i]
        DP[j, i + 1] = v % P

# print(DP)
print(DP[S, N])
```

Submitted correctly to the sample data, but 13 TLEs.
I think it's possible to compute it all together with numpy without looping about j, but it's a pain to think about, so [[numba]] is the solution!

AC [https://atcoder.jp/contests/abc169/submissions/14608435](https://atcoder.jp/contests/abc169/submissions/14608435)

---
This page is auto-translated from [/nishio/ABC169 F](https://scrapbox.io/nishio/ABC169 F) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
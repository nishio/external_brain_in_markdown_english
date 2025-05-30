---
title: "DP I"
---

[I - Coins](https://atcoder.jp/contests/dp/tasks/dp_i)
- Given a number of coins and the probability of each of them being heads, the problem of finding the probability that the number of heads is greater than the number of tails.
- The number of coins that are face up when looking at the coins from the top is the domain of definition, and the value is the probability of the coin being face up.
from  [[dynamic programming]]

    - [[Probability DP]]
- Python TLE PyPy AC
python

```
def solve(N, probs):
    m = [0.0] * (N + 1)
    m[0] = 1.0

    for i in range(N):
        n = [0.0] * (N + 1)
        for j in range(N):
            n[j + 1] += m[j] * probs[i]
        for j in range(N + 1):
            n[j] += m[j] * (1 - probs[i])
        m = n
    return sum(m[N // 2 + 1:])
```

[https://atcoder.jp/contests/dp/submissions/14880753](https://atcoder.jp/contests/dp/submissions/14880753)

---
This page is auto-translated from [/nishio/DP I](https://scrapbox.io/nishio/DP I) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
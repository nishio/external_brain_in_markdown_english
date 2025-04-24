---
title: "DP D"
---

[D - Knapsack 1](https://atcoder.jp/contests/dp/tasks/dp_d)
- The problem of maximizing value below a specified weight limit
    - [[backpack]]
- DP with weight as the domain of definition and maximum value at that weight as the value.

- PyPy 166 ms
- Mistake forgetting to update the maximum weight case by forgetting +1 in `for j in range(W - weight + 1)`.
python

```
def solve(N, W, WV):
    values = [0] * (W + 1)
    for i in range(N):
        next_values = values[:]
        weight, value = WV[i]
        for j in range(W - weight + 1):
            next_values[j + weight] = max(
                values[j + weight],
                values[j] + value)
        values = next_values
    return max(values)
```


---
This page is auto-translated from [/nishio/DP D](https://scrapbox.io/nishio/DP D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "DP E"
---

[E - Knapsack 2](https://atcoder.jp/contests/dp/tasks/dp_e)
- Maximize value below a specified weight limit [[backpack]] Issue
- But the space of weight limit is too large to make DP with weight as the defining region.
    - [[Exchange of value range and definition range]], define a value range, and do a DP where the value is the minimum weight that achieves that value.

from  [[dynamic programming]]
DP_E
- Problem statement [E - Knapsack 2](https://atcoder.jp/contests/dp/tasks/dp_e)

    - [[Exchange of value range and definition range]]
    - The space of weights is 10^11
    - The space of values is 10^5
    - In [[DP_D]], a function of value was created using weight as the domain of definition, and the maximum value was obtained
    - That approach is too broad a definitional area for this issue.
    - So, conversely, we create a function of weight with value as the domain of definition.
        - Then find the largest subscript in the domain whose weight satisfies the constraint
    - ![image](https://gyazo.com/8f6820c6fa358d709bd62c806b3166fb/thumb/1000)

python

```
def solve(N, W, WV):
    MAX_VALUE = N * 10 ** 3
    weights = [INF] * (MAX_VALUE + 1)
    weights[0] = 0
    for i in range(N):
        next_weights = weights[:]
        weight, value = WV[i]
        for j in range(MAX_VALUE - value + 1):
            next_weights[j + value] = min(
                weights[j + value],
                weights[j] + weight)
        weights = next_weights
    for i in range(MAX_VALUE, -1, -1):
        if weights[i] <= W:
            return i
```


---
This page is auto-translated from [/nishio/DP E](https://scrapbox.io/nishio/DP E) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
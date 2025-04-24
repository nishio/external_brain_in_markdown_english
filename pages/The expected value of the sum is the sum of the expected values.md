---
title: "The expected value of the sum is the sum of the expected values"
---

$E[X+Y] = E[X] + E[Y]$
$E\left[\sum_i X_i\right] = \sum_iE[X_i]$

proof
- $E[X + Y] = \sum_x\sum_y (x + y) P(X=x, Y=y)$ ...  [[Definition of expected value]]
- $= \sum_x\sum_y x P(X=x, Y=y) + \sum_x\sum_y y P(X=x, Y=y)$ ...  [[Change the order of addition]]
- $= \sum_x x \sum_y P(X=x, Y=y) + \sum_y y \sum_x P(X=x, Y=y)$ ... Constant bracketing
- $= \sum_x x P(X=x) + \sum_y y P(Y=y)$ ...  [[marginalization]]
- $= E[X] + E[Y]$ ...  [[Definition of expected value]]


- [[Expected number of times]]
    - [[The number of times is the sum]]
- $\#\{x\in X | f(x) \} = \sum_{x\in X} [f(x)]$
- ![image](https://gyazo.com/815c8001c4a4f32e92c5b96b004c4ef1/thumb/1000)

- $E_Y\left[\sum_{x\in X} [f(x, y)] \right] = \sum_{y\in Y}\sum_{x\in X} [f(x, y)]p(Y=y) =  \sum_{x\in X} E_Y[[f(x, y)]]$
- This is not peripheral...

- [[linearity of expectation]]

- [[Change order of operations]]

---
This page is auto-translated from [/nishio/和の期待値は期待値の和](https://scrapbox.io/nishio/和の期待値は期待値の和) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "Estimated sales from rankings"
---

One sales ranking was "1 for first place, 2 for second place, and 5 tied for fourth place". What information can we glean from this regarding sales?

- It is unknown how many different products are subject to the ranking; let N be the number of products.
- Sales $X_i (0 \leq i < N)$ within a given period are unknown. In a straightforward way, X follows a Poisson distribution.
- The parameter $\lambda_i$ of the Poisson distribution is unknown. The range is greater than or equal to 0 with no upper bound.
- Sampling from a uniform distribution of $0 \leq \lambda_i < M$ as an uninformed distribution since the distribution of lambda is unknown.
- Sampling from the Poisson distribution of its parameters.
- Only those items that satisfy the condition of "1 in 1st place, 2 in 2nd place, and 5 in 4th place with the same ratio" are taken out (rejection sampling).

Probability of occurrence of a ranking satisfying the condition at M=(1, 2, 3, 4, 5, 10, 20) when N=20.
Conditional probability of occurrence if code:M is given:.
- 1 0.0149075730471
- 2 0.0170706725845
- 3 0.0149454491107
- 4 0.0165070980522
- 5 0.010323113451
- 10 0.00249382777625
- 20 0.000251332059918
So the highest probability of occurrence is when M=2.

In that case, the number of sales for the first, second and fourth places are (4, 3, 2): 40%, (3, 2, 1): 23%, (5, 3, 2): 134
Number of occurrences in 1000 sampling:.

```
(4, 3, 2): 403, (3, 2, 1): 225, (5, 3, 2): 134
```


The same experiment for N=40 shows that the highest probability of occurrence (0.024) is when M=3. In that case, (5, 4, 3) is 44%.
Number of occurrences in 1000 sampling:.

```
(5, 4, 3): 441, (6, 4, 3): 194, (6, 5, 4): 136
```


N=80 also shows that M=3 has the highest probability of occurrence (0.002), in that case (6, 5, 4) is 56%.
Number of occurrences in 1000 sampling:.

```
(6, 5, 4): 563, (7, 5, 4): 174, (8, 5, 4): 70,
```


Note that the probability of occurrence when N=10, M=2 is 0.0097 and when N=15, M=2 is 0.029, so N is probably just under 20.

Conclusion: probably only 3-5 books sold even at #1 (sad)

python:

```
buf = []
num_samples = 0
while True:
    lambdas = np.random.random(NUM_BOOKS) * MAX_LAMBDA
    sample = np.random.poisson(lambdas)
    sample.sort()
    sample = sample[::-1]
    num_samples += 1
    if (sample[0] > sample[1] and sample[1] == sample[2] and
        sample[2] > sample[3] and sample[3] == sample[7] and
        sample[7] > sample[8]):
        buf.append((sample[0], sample[1], sample[3]))
        if len(buf) == 1000: break
```



---
This page is auto-translated from [/nishio/ランキングから売り上げ推定](https://scrapbox.io/nishio/ランキングから売り上げ推定) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "DP J"
---

from  [[dynamic programming]]
- Problem statement [J - Sushi](https://atcoder.jp/contests/dp/tasks/dp_j)
    - The problem of finding the time required to reach the end state by repeating stochastic transitions
    - The state is the domain of definition and the expected time required is the value [[Expected DP]].

[[DP_J]]
    - [[Unordered columns are multisets]]
    - If the problem deals with a column of some kind, and replacing any element of the column does not affect the problem, the ordered column is not necessary for the problem.
        - When the column length is N and the value range is M, M^N in ordered
        - If you take away the order, you get [[multiset]], and you can have N^M since you can have the number of pieces per value.
        - In the case of this problem, there are 100 things that take 4 different values, so if we do it naively, it's 4^100, but this becomes 100^4, which is much narrower.
    - [[Expected DP]]
    - Expected time required DP" is a concept that would be clearer if it were called "[[Expected time required DP]]".
        - The problem of finding the expected value of the time to reach a certain end state when the so-called "probability distribution", with the state as the domain of definition and probability as the value, changes to another distribution with stochastic transitions in a single step of operation.
        - Instead of simply repeating the update of one step, the DP has an "expected time to reach the end state" as a value, and the expected value of the start state is obtained by calculating from the fact that the value is 0 in the end state.
- A simpler question is, "Given four stepping stones, with a 1/2 chance of moving on to the next stone, what is the expected time to reach the goal?" Consider the following
    - ![image](https://gyazo.com/baf9dfe526c87ec53abf6f66fa139c33/thumb/1000)
    - Consider a DP that values the expected value of time required
    - One step after a, we are at 1/2 a and 1/2 b.
        - Multiply the probabilities and add them together to get "the expected value after one step of a."
        - A appears on both sides of the equation.
            - Because it has a 1/2 chance of self-transitioning.
            - To put things in perspective, we get an expression for a from b
- Transitions in this issue
    - ![image](https://gyazo.com/378d95d81f847f835f305597f00c264f/thumb/1000)

- 12 TLE when implemented naively.
python

```
def solve(N, AS):
    "void()"
    from collections import Counter
    count = Counter(AS)
    expect = {}
    expect[(0, 0, 0)] = 0

    def f(a, b, c):
        if (a, b, c) in expect:
            return expect[(a, b, c)]
        p = 1.0
        if a > 0:
            p += f(a - 1, b, c) * a / N
        if b > 0:
            p += f(a + 1, b - 1, c) * b / N
        if c > 0:
            p += f(a, b + 1, c - 1) * c / N
        p *= N / (a + b + c)

        # debug("f: a,b,c,p", a, b, c, p)
        expect[(a, b, c)] = p
        return p

    return f(count[1], count[2], count[3])
```


Slightly rewritten AC
python

```
def solve(N, AS):
    from collections import Counter
    count = Counter(AS)
    expect = [[[-1] * (N + 1) for i in range(N + 1)] for j in range(N + 1)]
    expect[0][0][0] = 0

    def f(a, b, c):
        p = N
        if a > 0:
            v = expect[a - 1][b][c]
            if v == -1:
                v = f(a - 1, b, c)
            p += v * a
        if b > 0:
            v = expect[a + 1][b - 1][c]
            if v == -1:
                v = f(a + 1, b - 1, c)
            p += v * b
        if c > 0:
            v = expect[a][b + 1][c - 1]
            if v == -1:
                v = f(a, b + 1, c - 1)
            p += v * c
        p /= (a + b + c)

        # debug("f: a,b,c,p", a, b, c, p)
        expect[a][b][c] = p
        return p

    return f(count[1], count[2], count[3])
```


---
This page is auto-translated from [/nishio/DP J](https://scrapbox.io/nishio/DP J) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
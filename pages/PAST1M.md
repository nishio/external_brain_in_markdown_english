---
title: "PAST1M"
---

[M - Leave it to us](https://atcoder.jp/contests/past201912-open/tasks/past201912_m)
![image](https://gyazo.com/6e7b0970c5ef90359fec6baba959c845/thumb/1000)

- Thoughts.
    - The problem of finding a selection method that maximizes the ratio
    - I wonder if there is anything to be said regarding the ratio's small and large.
    - 3/1 and 200/100, the former is larger, but the latter is larger when 0/100 is added
    - [http://www.asahi-net.or.jp/~vd7t-ktgw/other_favorites/programmingcontest/ProgrammingContest.html](http://www.asahi-net.or.jp/~vd7t-ktgw/other_favorites/programmingcontest/ProgrammingContest.html)
        - DP issues on ratios
            - [https://atcoder.jp/contests/abc054/tasks/abc054_d](https://atcoder.jp/contests/abc054/tasks/abc054_d)
        - Not this time, because the range of values is 10^5.
- Official Explanation
    - Instead of maximizing the ratio directly, make it a question of determining whether the ratio exceeds X
    - This can be determined by O(NlogN)
    - We can bisect the search for the possible range of ratios.
        - [[Maximize the sum ratio]]
- A thought I've had time to think about.
    - N is 1000, so a full 2^N search is not possible.
    - Can't we just greedily "add what makes it big"?
        - OK if "X1 < X1 + X2 then X1 + X3 < X1 + X2 + X3
python

```
from random import randint
for i in range(1000):
    a, b, c, d, e, f = [randint(1, 10) for i in range(6)]
    if a / b < (a + c) / (b + d) and (a + e) / (b + f) > (a + c + e) / (b + d + f):
        print(a, b, c, d, e, f)
        break
```

        - Easily found counterexamples: 5 8 5 7 8 7
        - [Maximize the sum ratio
    - Make it a question of determining whether X is exceeded or not.
        - $B_i - X A_i$ sign determination problem
        - Choose one of the largest from M
            - If all are negative, the maximum is 0 for "don't choose".
        - Sort and if the largest one is positive, OK.
            - [[dichotomous search]]
- 3WA
python

```
def solve(N, M, AS, BS, CS, DS):
    left = 0.0
    right = 1000000.0
    while left < right - 10 ** -7:
        x = (left + right) / 2
        y = max(DS[i] - x * CS[i] for i in range(M))
        zs = list(sorted([BS[i] - x * AS[i] for i in range(N)], reverse=True))
        if y > 0:
            y = y + sum(zs[:4])
        else:
            y = sum(zs[:5])

        if y >= 0:
            left = x
        else:
            right = x
    return left
```

    - RIGHT should be 10001, I set it to 1000000 more, but no change.
    - left < right - 10 ** -7 is smaller than the required 10 ** -6
    - Ah, okay, `if y > 0:` -> `if y > zs[4]:`.
        - →AC
        - When the best help has a negative score, the decision is "no gain, so don't use it", but due to the "must choose 5 animals" constraint, zs4 will be chosen if the help is not chosen, which could be an even bigger negative here.



- [[Problems admitting errors → bifurcation search]]
- [[First Algorithm Practical Skills Test]]

---
This page is auto-translated from [/nishio/PAST1M](https://scrapbox.io/nishio/PAST1M) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
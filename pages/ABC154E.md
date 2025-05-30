---
title: "ABC154E"
---

[E - Almost Everywhere Zero](https://atcoder.jp/contests/abc154/tasks/abc154_e)
![image](https://gyazo.com/3144c591c48ca98ba526eb541f2ade6d/thumb/1000)
- Thoughts.
        - [[Digit DP]] Right?
        - DP in table of 3 occurrences of non-zero numbers for 100 digits
        - There's a note in [[ABC154E_old]] about the wreckage you tried to solve earlier...
        - Can we make a library based on [[DP S]]?
    - What is Digit DP?
        - A dynamic programming algorithm that can be used when given a huge integer N, count up the number of things that satisfy the condition from non-negative integers less than or equal to N
        - When known for the upper i digits, use it to find the case of i+1 digits
        - In this case, if the sum of k non-zero digits in the upper i digits is x, then if 0 is added to the end of the sum, the sum will be i+1 digits as k. If 1 to 9, the sum will be k+1.
        - The only exception is when the upper i digits match N. Since 1 to 9 may exceed N, the i+1st digit of N must be taken care of.
python

```
def solve(N, K):
    less = [0] * (K + 2)
    equal = 0
    for v in N:
        new_less = [0] * (K + 2)
        if v != 0 and equal <= K:
            new_less[equal] += 1  # for 0
            new_less[equal + 1] += v - 1  # for 1..
            equal += 1

        for k in range(K + 1):
            new_less[k] += less[k]  # for 0
            new_less[k + 1] += 9 * less[k]  # for 1..9
        less = new_less

    ret = less[K]
    if equal == K:
        ret += 1
    return ret
```

- AC

---
This page is auto-translated from [/nishio/ABC154E](https://scrapbox.io/nishio/ABC154E) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
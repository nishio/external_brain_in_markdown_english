---
title: "ABC194F"
---

from [[ABC194]]

[F - Digits Paradise in Hexadecimal](https://atcoder.jp/contests/abc194/tasks/abc194_f)
![image](https://gyazo.com/1a17a7ce598564aed0e289ec0fd8e3cf/thumb/1000)
- Thoughts.
        - [[Digit DP]]
    - [[DP S]] copied and rewritten.
    - The sample went through, but it's slow, and the TLE is not resolving.
    - That's a tough one, since "record if 16 different numbers are already available" would be 60,000~ and updated 2 x 10^5 times.
- Official Explanation
    - I figured, "If I don't know what's already out there, I don't know if the number of numbers that have already appeared will increase the next time 1 appears, for example."
    - that is true
    - But since we are calculating 16 ways from 0 to F, even if we don't know which ones have already appeared, we can know "how many out of 16 will increase the number of appeared pieces".
    - Therefore, we only need to keep the number of numbers that have already appeared.
- Post-Contest AC
py

```
def solve(N, K):
    MOD = 1_000_000_007
    D = 16 + 1
    less = [0] * D
    equal_used = [0] * 16
    equal = 0
    for digit in N:
        digit = int(digit, 16)
        new_less = [0] * D
        for d in range(D):
            new_less[d] += less[d] * d

            if d == 0:
                new_less[d] += less[d] * 1
                new_less[d + 1] += less[d] * 15
            elif d != 16:
                new_less[d + 1] += less[d] * (16 - d)

        for new_digit in range(16):
            if new_digit < digit:
                new_d = equal
                if equal_used[new_digit] == 0:
                    new_d += 1
                if new_digit == 0 and equal == 0:
                    new_d = 0
                new_less[new_d] += 1

        for d in range(D):
            new_less[d] %= MOD
        less = new_less
        if equal_used[digit] == 0:
            equal += 1
            equal_used[digit] = 1
    ret = less[K]
    if equal == K:
        ret += 1
    return ret % MOD
```


---
This page is auto-translated from [/nishio/ABC194F](https://scrapbox.io/nishio/ABC194F) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
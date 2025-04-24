---
title: "ABC132D"
---

[D - Blue and Red Balls](https://atcoder.jp/contests/abc132/tasks/abc132_d)
- ![image](https://gyazo.com/b40880b288c4dd49649f7ecc52b89ecc/thumb/1000)
- Thoughts.
    - In short, I want to count up the arrangement of K blue balls into i non-contiguous groups
    - At least one red ball between groups.
    - K blue balls into i non-contiguous groups
        - ![image](https://gyazo.com/95d89bbd307f278fd1788557b7742f0e/thumb/1000)
        - $b_i = \binom{K-1}{i-1}$
    - N-K red balls are divided into i+1 groups, but both ends can be zero
        - ![image](https://gyazo.com/7e203a9a37997fafc1062cd78ebda967/thumb/1000)
        - $r_i = \binom{N-K+1}{i}$
    - Now all we need to do is calculate K cases of this.
        - Pre-calculate up to 2000 to speed up the process.
- Official Explanation
    - Policy OK
    - K is as small as 2000, so [[Pascal's triangle]] is acceptable without pre-calculation.
- AC
    - A naive implementation of the above policy could result in N - K - 1 < i in the calculation of ri.
        - Mathematically it is 0, but the implementation of the combination did not expect it and returned an incorrect value and WA'd.
        - I took care on the side of the library so as not to melt time with careless mistakes.
python

```
def main():
    N, K = map(int, input().split())
    MOD = 1_000_000_007
    c = Combination(N, MOD)
    for i in range(1, K + 1):
        r = c.comb(K - 1, i - 1)
        r *= c.comb(N - K + 1, i)
        r %= MOD
        print(r)
```



---
This page is auto-translated from [/nishio/ABC132D](https://scrapbox.io/nishio/ABC132D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
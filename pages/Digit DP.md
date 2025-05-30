---
title: "Digit DP"
---

Given a huge integer N, you can use the [[dynamic programming]] algorithm to count up the number of things that satisfy the condition from non-negative integers less than or equal to N.

Example of my implementation
- [[DP S]] An integer between 1 and K, where the sum of each digit in decimal notation is a multiple of D.
- [[ABC154E]] An integer greater than or equal to 1 and less than or equal to N and exactly K non-zero numbers when expressed in decimal notation.

- Use the information about the upper i digits to find the information for i+1 digits
    - [[ABC154E]]: Let x be the number of cases where k non-zero numbers are used in the upper i digits.
        - If the next digit is 0, it remains k, x ways; if 1 to 9, it becomes k+1, 9x ways.
python

```
for k in range(K + 1):
    new_less[k] += less[k]  # for 0
    new_less[k + 1] += 9 * less[k]  # for 1..9
```


- The only exception is when the upper i digits match N
    - 1-9 could exceed N
    - The i+1st digit of N needs to be taken care of.
        - The number of upper i digits matching N is always one way, so we have it by value, not by array.
        - Some of the explanations in the world make this an array too, but so far I haven't encountered a problem that requires it.

- If the last case matching N satisfies the condition, answer +1.
- If implemented naturally, the value is for "integers greater than or equal to 0", so depending on the problem conditions, the case of 0 is subtracted.





- [Introduction to Digit DP - torus711's thing](https://torus711.hatenablog.com/entry/20150423/1429794075)
- [https://atcoder.jp/contests/abc154/tasks/abc154_e](https://atcoder.jp/contests/abc154/tasks/abc154_e)

[https://maspypy.com/atcoder-参加感想-2019-02-16abc-155](https://maspypy.com/atcoder-参加感想-2019-02-16abc-155)

[[DIgit DP]]  [[dynamic programming]]

---
This page is auto-translated from [/nishio/桁DP](https://scrapbox.io/nishio/桁DP) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
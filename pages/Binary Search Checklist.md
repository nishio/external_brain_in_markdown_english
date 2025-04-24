---
title: "Binary Search Checklist"
---

![image](https://gyazo.com/3adb1ed9f7f843ada150d675bffb61a3/thumb/1000)
- Check the four components of [dichotomous search
- 1: Is f(x) correct?
    - I can't help it if I'm wrong here.
    - You should write down some patterns and check them out.
- 2: Does a large/small comparison involve an equal sign?
    - Depends on whether you choose left or right when there is no matching value.
    - ![image](https://gyazo.com/f387019b4af042257419dac27b4a501d/thumb/1000)
    - If it matches, that's it, if not, if we choose left, we need to search for f(x)=T and f(x)<T to be left, and then return left.
    - In [[abc174]]E it was necessary to return right in reverse
    - Some types of problems can't be separated from 1 and 2.
        - In that case, 1 becomes an implementation that returns bool.
- 3: Is the initial value of left appropriate?
    - Check whether the initial value satisfies the inequality to be satisfied by LEFT based on 2.
- 4: Is the initial value of right appropriate?

python

```
def solve(N, K, AS):
    left = 0  # (3)
    right = max(AS)  # (4)

    while left < right - 1:
        x = (left + right) // 2
        y = f(x)  # (1)
        if y > K:  # (2)
            left = x
        else:
            right = x
    return right
```



---
This page is auto-translated from [/nishio/二分探索チェックリスト](https://scrapbox.io/nishio/二分探索チェックリスト) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
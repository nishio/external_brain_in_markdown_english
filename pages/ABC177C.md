---
title: "ABC177C"
---

![image](https://gyazo.com/9aee3cdd36ebd15ec417f0041d2af303/thumb/1000)

from [[ABC177]]
ABC177C
[C - Sum of product of pairs](https://atcoder.jp/contests/abc177/tasks/abc177_c)
![image](https://gyazo.com/03b7a549020d2bc77a093d63cb5692b4/thumb/1000)
- Take everything out and square it, then draw a diagonal line and divide it in half.
- ![image](https://gyazo.com/9aee3cdd36ebd15ec417f0041d2af303/thumb/1000)
- If the value you want is S $2 S + \sum A_i^2 = (\sum A_i)^2$ # Distribution law [[Half of the queue]] [[Exchange of product and sum]].
- WA for naively truncating "divide by two" to a divisor.
    - If odd, add mods to make it an even number, then divide by 2
python

```
def solve(N, AS):
    sum = 0
    sumSq = 0
    for i in range(N):
        sum += AS[i]
        sum %= MOD
        sumSq += AS[i] * AS[i]
        sumSq %= MOD

    ret = (sum * sum - sumSq) % MOD
    if ret % 2 == 0:
        return ret // 2
    else:
        return (ret + MOD) // 2
```

- The official explanation is [[cumulative sum]], which is a way to multiply a row by a single multiplication.
    - They said my solution was "not simply divisible by two, so it would be a difficult solution using the inverse original."
        - It's just too abstract and difficult to think about.
    - If you've ever tried it with a number as small as 11, it's not hard to come up with.
python

```
xs = [None] * 11
for i in range(11):
    xs[i * 2 % 11] = i
# xs => [0, 6, 1, 7, 2, 8, 3, 9, 4, 10, 5]
```

    - There's an i in the second i like this.
    - The odd-numbered number gets a value in the second round once you get to the end.
- ![image](https://gyazo.com/b6ff3cebe067c26861dc9c4c51958d66/thumb/1000)
    - Hmmm, I guess it was 4ms short of the fastest!
    - The fastest code takes the surplus only at the end.
        - Is it faster to push through with long integers if the maximum is about 10^30?
            - [[Fast long integers]]

---
This page is auto-translated from [/nishio/ABC177C](https://scrapbox.io/nishio/ABC177C) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
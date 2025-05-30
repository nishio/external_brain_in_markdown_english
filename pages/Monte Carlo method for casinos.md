---
title: "Monte Carlo method for casinos"
---

I heard about a completely different concept from the original Monte Carlo method, called Monte Carlo in the field of gambling, and when I looked into it, well, it wasn't a proper strategy.
- Original Monte Carlo method: [Monte Carlo method - Wikipedia](https://ja.wikipedia.org/wiki/%E3%83%A2%E3%83%B3%E3%83%86%E3%82%AB%E3%83%AB%E3%83%AD%E6%B3%95)

Casino Monte Carlo method (for 2x payout)
- Write 1, 2, 3 on a piece of paper.
- A: Bet x, the number of both ends added together
- If you win, erase both ends of the row.
- If you lose, add an x on the far right.
- Return to A if column length is not 1.

First of all, the length of the column is 3 at the beginning, 2 shorter if you win, 1 more if you lose, and in the "lose-win-win" order, the length of the column is 0... but let's stop when it is 0.
If you're unlucky, it'll go on for so long without stopping that you'll have to discontinue it after 100 times.
python

```
from collections import Counter
from random import random, seed
seed(1)


def f():
    xs = [1, 2, 3]
    ret = 0
    for i in range(100):
        if len(xs) < 2:
            break
        x = xs[0] + xs[-1]
        ret -= x
        if random() < 0.5:
            ret += 2 * x
            xs = xs[1:-1]
        else:
            xs.append(x)
    return ret


c = Counter(f() for i in range(1000000))
```


The following is a list of the 20 most frequently profitable sessions, in descending order of frequency of profit per session, after a million experiments
- You can see that you gain a little at a high probability and lose a lot at a low probability.
- The session ends with a gain of about 94%.
- The expected value when gaining is 4.2
- Expected value of loss is -75.6
- The most loss-making case is -829536 in this experiment
:

```
[(4, 499951),
 (6, 236607),
 (3, 124839),
 (2, 38641),
 (1, 29213),
 (-1, 12488),
 (0, 10124),
 (-2, 6393),
 (-3, 5220),
 (-4, 4173),
 (-5, 3570),
 (-7, 2559),
 (-6, 2437),
 (-8, 2084),
 (-10, 1535),
 (-11, 1433),
 (-9, 1363),
 (-12, 1042),
 (-13, 960),
 (-14, 857)]
```


Is it strange to lose 830,000 yen?
- Not funny.
- If you repeatedly win enough to lose once and not end up losing, your wager increases every time you lose, and when you win, your wager does not decrease and the left edge disappears, increasing the "incremental amount of your wager when you lose" and entering a bad cycle because this "incremental amount of your wager" is your past wager.
    - [https://gist.github.com/nishio/877c13738786d35fd7fbfae243e649c5](https://gist.github.com/nishio/877c13738786d35fd7fbfae243e649c5)

---
This page is auto-translated from [/nishio/カジノのモンテカルロ法](https://scrapbox.io/nishio/カジノのモンテカルロ法) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
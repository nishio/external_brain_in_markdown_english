---
title: "PAST2I"
---

from  [[Second Algorithm Practical Skills Test]]
![image](https://gyazo.com/edc8d1afb55b0c9082e68b8470ffa0e0/thumb/1000)
[I - Tournament](https://atcoder.jp/contests/past202004-open/tasks/past202004_i)

PAST2I
- If you know your opponent's ID, you know if you win or lose by a constant order of magnitude.
- So just queue up the first round winner ID and read it in the second round.
- While len(winner) > 2` since there is no need to do a final.
python

```
def solve(N, AS):
    ranks = [1] * (2 ** N)
    winner = list(range(2 ** N))
    next_rank = 2

    while len(winner) > 2:
        next_winner = []
        for i in range(0, len(winner), 2):
            a = winner[i]
            b = winner[i + 1]
            if AS[a] > AS[b]:
                next_winner.append(a)
                ranks[a] = next_rank
            else:
                next_winner.append(b)
                ranks[b] = next_rank
        winner = next_winner
        next_rank += 1
    return ranks
```



---
This page is auto-translated from [/nishio/PAST2I](https://scrapbox.io/nishio/PAST2I) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "AGC044A"
---

AC

Starting from 0, the operation is repeated to N, either 2x, 3x, 5x, plus or minus 1. Each of the four types of operations has a defined cost, and the minimum cost is found [problem [https://atcoder.jp/contests/agc044/tasks/agc044_](https://atcoder.jp/contests/agc044/tasks/agc044_) a].

Instead of going from 0 to N as the problem states, we will go from N to 0, and avoid the trap of "doing too many +1's and eating up time" by making the choices four: "move up to a multiple of 2 and divide by 2", "do the same for 3", "do the same for 5", and "move up to 0". [time reversal (physics)

Starting from N, the above four operations are performed on the "largest unexplored number (vertex)". Because all operations decrease the number, the largest number has no other choice but to reach that number, and it is determined that the "tentative minimum score" is truly the minimum score.

I put the "tentative minimum score" for each vertex into a Python dict. You don't want to put it in an array because the definition range is 10^18.

I usually kind of do INF=10**10 or something and think "that's good enough", but this problem N is 10^18 max and each cost is 10^9 max, so it easily exceeds. It subtly WAs. I haven't thought about how much is the theoretical maximum, but I'll keep it a large enough number.

AC in pure Python
python

```
INF = 10 ** 27 + 1
def solve(N, A, B, C, D):
    to_visit = [-N]
    cost = {N: 0}

    def put(n, c):
        cost[n] = min(cost.get(n, INF), c)
        heappush(to_visit, -n)

    visited = N + 1
    while to_visit:
        n = -heappop(to_visit)
        if n == visited:
            continue

        visited = n
        c = cost[n]
        put(0, c + n * D)

        if n % 2 == 0:
            put(n // 2, c + A)
        else:
            put((n+1) // 2, c + A + D)
            put((n-1) // 2, c + A + D)

        if n % 3 == 0:
            put(n // 3, c + B)
        elif n % 3 == 1:
            put((n-1) // 3, c + B + D)
            put((n+2) // 3, c + B + D * 2)
        else:
            put((n+1) // 3, c + B + D)
            put((n-2) // 3, c + B + D * 2)

        if n % 5 == 0:
            put(n // 5, c + C)
        elif n % 5 == 1:
            put((n-1) // 5, c + C + D)
            put((n+4) // 5, c + C + D * 4)
        elif n % 5 == 2:
            put((n-2) // 5, c + C + D * 2)
            put((n+3) // 5, c + C + D * 3)
        elif n % 5 == 3:
            put((n+2) // 5, c + C + D * 2)
            put((n-3) // 5, c + C + D * 3)
        elif n % 5 == 4:
            put((n+1) // 5, c + C + D)
            put((n-4) // 5, c + C + D * 4)

    return cost[0]
```

[https://atcoder.jp/contests/agc044/submissions/14679372](https://atcoder.jp/contests/agc044/submissions/14679372)


- [[Digit DP]]
[[AGC044]] [[atcoder]]

---
This page is auto-translated from [/nishio/AGC044A](https://scrapbox.io/nishio/AGC044A) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
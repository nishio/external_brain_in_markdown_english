---
title: "PAST2M"
---

from  [[Second Algorithm Practical Skills Test]]
![image](https://gyazo.com/b74deda81b8400cfd3e8c683aff07100/thumb/1000)
[m - cafeteria](https://atcoder.jp/contests/past202004-open/tasks/past202004_m)

PAST2M
- Thoughts.
    - 0 when the favorite dish is 0.
    - Otherwise, the pattern will be Period D, starting with the timing of your favorite dish.
        - Divide L by D.
    - But if I calculate the pattern of period D for each of the N employees, 10^10 will not make it, what should I do?
- Official Explanation
    - ![image](https://gyazo.com/c60e3ee7a911c22c643bb530acf812c6/thumb/1000)
- A new thought.
    - L is constant regardless of employees
    - If I know the next day the same favorite menu item is served, I know how many times I'll eat a menu item I don't like in between.
    - Tj varies from person to person, 10^9
        - Requires processing on the order of less than linear
        - Doubling to logarithmic order
    - The problem of finding x when f(x) = y by doubling the sum f(x) of the number of times you ate your favorite dish x times.
            - [[Since it is monotonically increasing, it can be inverse-functioned by a binary search.]]
- mounting
    - The specification is complex, so for the sake of clarity, I implemented it naively first
    - sample AC:
python

```
def solve(D, L, N, CS, KFTS):
    for K, F, T in KFTS:
        F -= 1  # 1-origin to 0-origin
        ret = 0
        if CS[F % D] == K:
            ret = 1
        countdown = T - 1
        cur = F
        prev = cur
        while countdown:
            cur += 1
            if CS[cur % D] == K:
                ret += 1
                prev = cur
                countdown -= 1
            elif cur - prev == L:
                prev = cur
                countdown -= 1
        print(ret)
```

    - I didn't take the extra and forgot that RE and F are 1-origin and did WA and so on.
    - The problem is that this while countdown is 10^9.
    - The commentary dubbed it one step to the next favorite dish, but if you're going to dub it anyway, why not just one step per day?
        - No, because if you don't use your favorite dish as a starting point, you won't be able to determine how many dishes you don't like to eat.
    - A version that records the location of the "next same dish" in advance and skips ahead once a favorite dish is found.
python

```
def solve(D, L, N, CS, KFTS):
    MAX_C = 10 ** 5
    first = [None] * MAX_C
    prev = [None] * MAX_C
    next = [None] * D
    for i, d in enumerate(CS):
        d -= 1  # to 0-origin
        if first[d] is None:
            first[d] = i
            prev[d] = i
        else:
            next[prev[d]] = i
            prev[d] = i
    for d in range(MAX_C):
        if prev[d] is not None:
            next[prev[d]] = D + first[d]

    for K, F, T in KFTS:
        F -= 1  # 1-origin to 0-origin
        ret = 0
        if CS[F % D] == K:
            ret = 1
        countdown = T - 1
        cur = F
        prev = cur
        while countdown:
            cur += 1
            if CS[cur % D] == K:
                ret += 1
                countdown -= 1
                while True:
                    n = next[cur % D]
                    d = n - cur
                    if d < 0:
                        d += D
                    up = (d - 1) // L + 1
                    if countdown >= up:
                        countdown -= up
                        cur = n
                        ret += 1
                        continue
                    else:
                        countdown = 0
                        break

            elif cur - prev == L:
                prev = cur
                countdown -= 1
        print(ret)
```

    - [diff](https://github.com/nishio/atcoder/commit/30e20a9f78f7581bd1022fb6ad97708f832a8a26)
    - Next, we'll dub this "moving on" section.
        - Scope.
            - Worst case scenario, if the next plate is next to it, the number of dishes is only +1, so it takes 10^9 times to get to 10^9.
            - 2^30 would certainly be over, `[0, 30)` is OK.
    - Pre-calculation of up [diff](https://github.com/nishio/atcoder/commit/58152e4dbc000087e797bbdaa122b1a0da453de1)
        - This is one step
    - doubling
        - I didn't realize I needed the value of next for doubling ups, and I implemented it wrong once.
python

```
# doubling
db_next = [next]
db_ups = [ups]
for _i in range(1, 30):
    next = db_next[-1]
    ups = db_ups[-1]
    new_next = []
    new_ups = []
    for i in range(D):
        n1 = next[i] % D
        n2 = next[n1]
        u1 = ups[i]
        u2 = ups[n1]
        new_next.append(n2)
        new_ups.append(u1 + u2)
    db_next.append(new_next)
    db_ups.append(new_ups)
```

        - [[Doubling → Bifurcation search]].
python 

```
for i in range(30 - 1, -1, -1):
    up = db_ups[i][cur % D]
    if countdown >= up:
        countdown -= up
        cur = db_next[i][cur % D]
        ret += 2 ** i
```

    - [diff](https://github.com/nishio/atcoder/commit/6997c0a4921fe135107fbc2d7448a56abb4535f9)
- You're still going to TLE on this one, right? (19 TLE to 10 TLE)
    - Oh, right, people who don't have a favorite dish will run 10^9.
python

```
if first[K - 1] is None:
    print(0)
    continue
```

- Still, 4TLE.
    - It's not good that you're asking for a loop of "the first day your preferred dish appears after F."
    - Let's bifurcate this one, too.
    - [AC](https://atcoder.jp/contests/past202004-open/submissions/18976077)
    - [diff](https://github.com/nishio/atcoder/commit/c0ea2d3a7520573486f6552aa6ee854b5cd0fe66)

---
This page is auto-translated from [/nishio/PAST2M](https://scrapbox.io/nishio/PAST2M) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
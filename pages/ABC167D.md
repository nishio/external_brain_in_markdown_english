---
title: "ABC167D"
---

python

```
def solve(N, K, xs):
    "void()"
    town_to_time = np.zeros(N, np.uint16)
    time_to_town = np.zeros(N, np.uint16)
    cur = 1
    for i in range(K):
        cur = xs[cur - 1]
        # print(town_to_time, time_to_town, cur)
        if town_to_time[cur - 1]:
            # visited before
            period = i + 1 - town_to_time[cur - 1]
            rest = K - i - 1
            rest %= period
            # print(rest, town_to_time[cur - 1], town_to_time[cur - 1] + rest)
            print(time_to_town[town_to_time[cur - 1] + rest - 1])
            return

        town_to_time[cur - 1] = i + 1
        time_to_town[i] = cur
    print(cur)
```


AC: 42, WA: 15, max_time: 0.34
np.uint16
np.uint32

AC

---
This page is auto-translated from [/nishio/ABC167D](https://scrapbox.io/nishio/ABC167D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
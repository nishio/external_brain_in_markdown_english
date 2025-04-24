---
title: "ABC006C"
---

[C - Riddle of the Sphinx](https://atcoder.jp/contests/abc006/tasks/abc006_3)
- ![image](https://gyazo.com/2f6b59dcf7787876c9b5f7e08d21cb47/thumb/1000)
- Thoughts.
    - Assuming they are all 2, the problem is to make up a maximum of N combinations of +1 or +2 for the extra number.
    - A naive double loop will not make it in time.
    - If the remainder is less than or equal to N, just give that number of 1's.
    - If the remainder is more than N, we can make them all 3 and assign the remainder to 4.
    - Constant Order
- Official Explanation
    - It's kind of a totally different story.
        - If you decide on one, you can do a Tsurugame count, so you do a full search for one, or you can find out that the old man is 0/1, so you do a full search for the rest.
    - AC with the above solution without searching.
python

```
def solve(N, M):
    IMPOSSIBLE = (-1, -1, -1)
    x = M - 2 * N
    if x < 0:
        return IMPOSSIBLE
    if x <= N:
        return (N - x, x, 0)
    x -= N
    if x <= N:
        return (0, N - x, x)
    return IMPOSSIBLE
```


- [[landing practice]]
- [[Small order from official]]
[[ABC006]]

---
This page is auto-translated from [/nishio/ABC006C](https://scrapbox.io/nishio/ABC006C) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
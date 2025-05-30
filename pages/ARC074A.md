---
title: "ARC074A"
---

[C - Chocolate Bar](https://atcoder.jp/contests/arc074/tasks/arc074_a)
- ![image](https://gyazo.com/e5a08f96669cd40e7509f03bf2e5fd9d/thumb/1000)
- Thoughts.
    - If either length or width is a multiple of 3, just trisect.
    - When dividing into 1 and 2 and then splitting the 2, bisection is optimal if possible
        - Because otherwise, the farther away you are, the further away you are.
    - Can you say it is 1/3 floor or ceil?
        - I can tell you if you can do the bisecting...
        - Either floor or ceil can be bisected.
            - So we're going in circles.
        - It seems to be possible even if it cannot be bisected.
            - When there is another division y between one division and 1/3, y is always better
            - ...hmmm, there are so many different cases, it's a pain in the ass.
- AC
python

```
def solve(H, W):
    if W % 3 == 0:
        return 0

    def f(x):
        ret = []
        a1 = H * x
        if H % 2 == 0:
            a2 = (H // 2) * (W - x)
            ret.append(abs(a2 - a1))
        elif (W - x) % 2 == 0:
            a2 = H * ((W - x) // 2)
            ret.append(abs(a2 - a1))
        else:
            ar = H * (W - x)
            a2 = H // 2 * (W - x)
            a3 = ar - a2
            ret.append(max(a1, a2, a3) - min(a1, a2, a3))
            a2 = H * ((W - x) // 2)
            a3 = ar - a2
            ret.append(max(a1, a2, a3) - min(a1, a2, a3))
        return min(ret)

    return min(f(W // 3), f(W // 3 + 1))


def main():
    H, W = map(int, input().split())
    print(min(solve(H, W), solve(W, H)))
```

- Official Explanation
    - I'm doing a full search on one side, and the other side is determined by FLOOR for each of the vertical and horizontal divisions.

python

```
def solve(H, W):
    if W % 3 == 0:
        return 0

    def f(x):
        ret = []
        a1 = H * x
        ar = H * (W - x)
        a2 = H // 2 * (W - x)
        a3 = ar - a2
        ret.append(max(a1, a2, a3) - min(a1, a2, a3))
        a2 = H * ((W - x) // 2)
        a3 = ar - a2
        ret.append(max(a1, a2, a3) - min(a1, a2, a3))
        return min(ret)

    return min(f(W // 3), f(W // 3 + 1))


def main():
    H, W = map(int, input().split())
    print(min(solve(H, W), solve(W, H)))
```


---
This page is auto-translated from [/nishio/ARC074A](https://scrapbox.io/nishio/ARC074A) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
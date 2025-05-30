---
title: "DP L"
---

[L - Deque](https://atcoder.jp/contests/dp/tasks/dp_l)
- Competitive Game Read-Out Issues
- DP with the board as the domain of definition
    - The board can be represented by a range
- There is no need to distinguish between the first and the second hand.
    - Maximize "my score - opponent's score" for both the first and second moves.
- Unmemorized naive recursion.
    - All sample codes succeed.
python

```
def solve(N, XS):
    def first(L, R):
        # debug(": L, R", L, R)
        if L == R:
            return XS[L]
        return max(
            XS[L] - first(L + 1, R),
            XS[R] - first(L, R - 1)
        )

    return first(0, N - 1)
```


Compile in Cython because it is TLE as it is.
- I put in an array that has a value that cannot be taken to make sure it has not been calculated, but since it can be both positive and negative, I also created an array that has a value that has been calculated or not.
    - You could have left the value large enough.
- I used int because it was an error to use bool.
cython

```
cdef long[3000 * 3000] memo
cdef int[3000 * 3000] done

cdef first(L, R):
    if L == R:
        return XS[L]
    pos = L * N + R
    if done[pos + N]:
        right = memo[pos + N]
    else:
        right = first(L + 1, R)

    if done[pos - 1]:
        left = memo[pos - 1]
    else:
        left = first(L, R - 1)

    ret = XS[L] - right
    x = XS[R] - left
    if x > ret:
        ret = x
    memo[pos] = ret
    done[pos] = True
    return ret


cdef solve():
    for i in range(N * N):
        memo[i] = 0
        done[i] = False

    return first(0, N - 1)


def main():
    global N, XS
    # parse input
    N = int(input())
    XS = list(map(int, input().split()))
    print(solve())
```

[https://atcoder.jp/contests/dp/submissions/15060096](https://atcoder.jp/contests/dp/submissions/15060096)

---
This page is auto-translated from [/nishio/DP L](https://scrapbox.io/nishio/DP L) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
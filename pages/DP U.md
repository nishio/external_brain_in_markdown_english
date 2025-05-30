---
title: "DP U"
---

[U - Grouping](https://atcoder.jp/contests/dp/tasks/dp_u)
- Divide N elements into arbitrary groups, the score is determined by the way of division, and the problem is to maximize the score.

- If there are two elements, just put them in the same group if the score is positive, and put them in different groups if the score is negative.
    - But when you add a third element, if this one's connection to the other elements is strong, you'll say, "I knew I should have put them in the same group.
    - Is the DP to find the score for each k-1 grouping based on the score for each additional one?
        - Is that an exponential order, since each grouping cannot be equated?
        - Oh, N is the maximum 16? Maybe that's all right.
        - This way, the first element will be in one group, the next element can join it or become a new group in two ways, and the third element...
            - ![image](https://gyazo.com/6f38fa909ae869e3d950faf49d9fd560/thumb/1000)
            - Hmmm, it's going to be hard to update this grouping of data structure.
- Reading the explanation, I found the opposite approach, "divide a given set into two", I see.
    - [EDPC Explanation U to Z - kyopro_friends' diary](https://kyopro-friends.hatenablog.com/entry/2019/01/12/231106)
- Start with the whole set and compute back with [memory recursion
    - Score 0 if the given set has 1 element
    - There is an option to not split a given set
    - It doesn't affect anything outside the given set, so just return the maximum score.
- Scores per group
    - Since any subset S is used once anyway, let's compute and cache it for all subsets first!
    - I think I could DP this calculation process itself.
        - I didn't have to do it, I had AC, so I didn't become one.

Score calculation per group
- Double loop for elements of a given set
python

```
def calcScore(S):
    debug("enter calcScore: S", S)
    x = S
    ret = 0
    i = 0
    while x:
        if x & 1:
            debug(": i", i)
            for j in range(i):
                if (S >> j) & 1:
                    debug(": i, j, M[i,j]", i, j, M[i, j])
                    ret += M[i, j]
        x //= 2
        i += 1
    debug("leave calcScore: ret", ret)
    return ret
groupScore = [calcScore(i) for i in range(1 << N)]
```


[[subset enumeration]] of the given set
python

```
def solve(S):
    x = S
    while x > 0:
        print(f"{x:08b}")
        x = (x - 1) & S
```

:

```
>>> solve(14)
00001110
00001100
00001010
00001000
00000110
00000100
00000010

>>> solve(10)
00001010
00001000
00000010
```


When combined, it looks like this.
- It gives the correct answer to the sample case, but it's going to TLE. I need to rewrite the messy cache a little more seriously.
python

```
def solve(N, M):
    FULLBIT = (1 << N) - 1

    def calcScore(S):
        # debug("enter calcScore: S", S)
        x = S
        ret = 0
        i = 0
        while x:
            if x & 1:
                # debug(": i", i)
                for j in range(i):
                    if (S >> j) & 1:
                        # debug(": i, j, M[i,j]", i, j, M[i, j])
                        ret += M[i * N + j]
            x //= 2
            i += 1
        # debug("leave calcScore: ret", ret)
        return ret
    groupScore = [calcScore(i) for i in range(1 << N)]
    # debug(": groupScore", groupScore)

    from functools import lru_cache
    @lru_cache(maxsize=None)
    def sub(S):
        ret = groupScore[S]
        x = (S - 1) & S
        while x > 0:
            y = (~x) & S
            v = sub(x) + sub(y)
            if v > ret:
                ret = v
            x = (x - 1) & S
        return ret

    return sub(FULLBIT)
```


AC enough to rewrite the cache.
python

```
    table = [None] * (1 << N)

    def sub(S):
        ret = table[S]
        if ret != None:
            return ret
        ret = groupScore[S]
        x = (S - 1) & S
        while x > 0:
            y = (~x) & S
            v = sub(x) + sub(y)
            if v > ret:
                ret = v
            x = (x - 1) & S
        table[S] = ret
        return ret
```

AC [https://atcoder.jp/contests/dp/submissions/15101926](https://atcoder.jp/contests/dp/submissions/15101926)

---
This page is auto-translated from [/nishio/DP U](https://scrapbox.io/nishio/DP U) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
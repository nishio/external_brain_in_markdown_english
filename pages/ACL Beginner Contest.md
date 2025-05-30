---
title: "ACL Beginner Contest"
---

Contests with questions that can use [[AtCoder Library]].

I realized after submitting C that I had made a careless mistake in B and corrected it, implemented D and passed the sample through before submitting it, but it was a WA, and when I saw E, I thought it was a [[Delayed propagation segment tree]], so I solved that one. I went back to D and realized "this is a segment tree and it's a DP", but at that point I had 10 minutes left. I couldn't make it in time.
![image](https://gyazo.com/cf293b51cdb0f3e61921e381956d2872/thumb/1000)

Wow, 9 more points and light blue! Too close to call!
![image](https://gyazo.com/9dabf4b98969d40e2b5509564cfe5ff0/thumb/1000)

[B - Integer Preference](https://atcoder.jp/contests/abl/tasks/abl_b)
- ![image](https://gyazo.com/f4f4a47bc47a888934ec7935d5699512/thumb/1000)
- careless mistake
    - Ugly conditional expression because it was fixed in a big hurry.
python

```
A, B, C, D = map(int, input().split())
# if A <= D <= B or A <= C <= B:  # NG
if A <= D <= B or A <= C <= B or C <= A <= D:
    print("Yes")
else:
    print("No")
```

- If you think about it calmly, it looks like this
python

```
A, B, C, D = map(int, input().split())
if D < A or B < C:
    print("No")
else:
    print("Yes")
```


[C - Connect Cities](https://atcoder.jp/contests/abl/tasks/abl_c)
- ![image](https://gyazo.com/d392de5b2ccc1dc816648fb819b6adbf/thumb/1000)
- Just count how many clumps of connected cities there are (let's say X) and draw a path from one of them to the remaining X-1 clumps.
- "connected urban mass" = [[linkage component]].
- So [[UnionFind]].
python

```
def solve(N, M, edges):
    init_unionfind(N)
    for e in edges:
        unite(e[0] - 1, e[1] - 1)

    s = set(find_root(x) for x in range(N))
    return len(s) - 1
```


[D - Flat Subsequence](https://atcoder.jp/contests/abl/tasks/abl_d)
- ![image](https://gyazo.com/13fcd06d7d09419948c239f846aedff7/thumb/1000)
- I don't know how to attribute this to ACL, so I'll write it plainly first.
- Submitted, but WA/TLE mixed.
    - Even if I could get a WA, it would be a TLE, and I don't have a clue how to resolve this, so I put it on hold and did an E.
- When I came back and reviewed it, I realized that it was [[segment tree]] and [[dynamic programming]], but I had 10 minutes left.
    - Dynamic programming where the trailing value is the definition range and the longest length is the value range
        - [[Collecting DP]]
    - When the i-th value is A, the max of the K values before and after A is the "longest sequence of values that can be connected to the i-th value," so update by adding 1 to it
    - Samples go through below.
python

```
def solve(N, K, AS):
    count = [0] * 300_000
    count[AS[0]] = 1
    for i in range(1, N):
        A = AS[i]
        start = max(0, A - K)
        best = max(count[start:A + K + 1])
        count[A] = best + 1
    return max(count)
```

- Point update range max, so segment trees can be used.
    - Segment tree version AC
python

```
def solve(N, K, AS):
    MAX_CAPACITY = 300_000
    set_width(MAX_CAPACITY + 10)

    count = [0] * SEGTREE_SIZE
    point_set(count, AS[0], 1, max)
    for i in range(1, N):
        A = AS[i]
        start = max(0, A - K)
        end = min(A + K + 1, MAX_CAPACITY + 1)
        best = range_reduce(count, start, end, max, -INF)
        point_set(count, A, best + 1, max)
    return range_reduce(count, 0, MAX_CAPACITY + 1, max, -INF)
```

    - Hammer Point
        - Python lists are allowed to have `count[start:end]` with end out of range, but segment trees are not
        - Need +1 because it contains `MAX_CAPACITY`.

[E - Replace Digits](https://atcoder.jp/contests/abl/tasks/abl_e)
- ![image](https://gyazo.com/2bd499438884da4227a67110c503b545/thumb/1000)
- I thought it might be a twin segment tree because of the range update.
- The process of "Calculate the remainder as a decimal number with 200,000 digits" is performed by [[range contraction]] for each query, so [[Delayed propagation segment tree]] is appropriate.
- I mistakenly thought the binary operation of the values to do this was `(a * 10 + b) % MOD`.
    - Actually, the number of digits on the right side is `(a * (10 ** size) + b) % MOD` as size
    - I reworked my own library in a big hurry because the binary operation does not take size as an argument.
    - another solution
        - >  E had (length, sum). I think having (10^n, sum) is computationally better without mod pow.
            - [twitter @maspy_stars](https://twitter.com/maspy_stars/status/1309859601483849733)

- Pre-calculate the remainder of `1111111111` or `10000000` since it will be a decimal number of 200,000 digits.
python

```
def main():
    # parse input
    N, Q = map(int, input().split())
    set_width(N + 1)

    value_unity = 0
    value_table = [value_unity] * SEGTREE_SIZE
    value_table[NONLEAF_SIZE:NONLEAF_SIZE + N] = [1] * N

    action_unity = None
    action_table = [action_unity] * SEGTREE_SIZE

    cache11 = {}
    i = 1
    p = 1
    step = 10
    while i <= N:
        cache11[i] = p
        p = (p * step + p) % MOD
        step = (step * step) % MOD
        i *= 2

    cache10 = {0: 1}
    i = 1
    p = 10
    while i <= N:
        cache10[i] = p
        p = (p * 10) % MOD
        i += 1

    def action_force(action, value, size):
        if action == action_unity:
            return value
        # return int(str(action) * size)
        return (cache11[size] * action) % MOD

    def action_composite(new_action, old_action):
        if new_action == action_unity:
            return old_action
        return new_action

    def value_binop(a, b, size):
        # return (a * (10 ** size) + b) % MOD
        return (a * cache10[size] + b) % MOD

    full_up(value_table, value_binop)
  
    for _q in range(Q):
        l, r, d = map(int, input().split())
        lazy_range_update(
            action_table, value_table, l - 1, r, d,
            action_composite, action_force, action_unity, value_binop)

        ret = lazy_range_reduce(
            action_table, value_table, 0, N, action_composite, action_force, action_unity,
            value_binop, value_unity)
        print(ret)
Someone wrote on Twitter that he solved it with [square partitioning].
```


F
- Counting frequency [[convolution]]?
    - DP with [[principle of inclusion]]?
- [https://www.hamayanhamayan.com/entry/2020/09/27/013201](https://www.hamayanhamayan.com/entry/2020/09/27/013201)
- [https://kmjp.hatenablog.jp/entry/2020/09/26/1030](https://kmjp.hatenablog.jp/entry/2020/09/26/1030)

---
This page is auto-translated from [/nishio/ACL Beginner Contest](https://scrapbox.io/nishio/ACL Beginner Contest) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "AISING Programming Contest 2020"
---

[Acing Programming Contest 2020 - AtCoder](https://atcoder.jp/contests/aising2020)
![image](https://gyazo.com/7de3589758d166915f760316cf5f6fb2/thumb/1000)

[C - XYZ Triplets](https://atcoder.jp/contests/aising2020/tasks/aising2020_c)
- ![image](https://gyazo.com/7a65641796a5dde7c39dff799a4e7c76/thumb/1000)
- Because of the squared terms, x,y,z is less than 100, and even if we do the whole search, it's 10^6, so there's plenty of room.
- The problem is that you have to do it n times.
- Once you write the code to do it N times naively without thinking about the details and confirm that it passes the test
    - 10^10
python

```
if v == n:
	ret += 1
elif v > n:
	break
```

- When the result of the calculation matches n, ret is increased, and when it is small, nothing is done.
- The loop for the outermost n is the largest one, and if we count the answers for smaller n in the process, we can say that we don't need a loop for n and rewrite it.
    - Where `n = N` originally had `for n in range(N)`.
python

```
def solve(N):
    from math import sqrt, floor
    ret = [0] * (N + 1)
    n = N
    for x in range(1, floor(sqrt(n))):
        v0 = x * x
        for y in range(1, floor(sqrt(n))):
            v1 = v0 + y * y + y * x
            if v1 >= n:
                break
            for z in range(1, floor(sqrt(n))):
                v = v1 + z * z + y * z + z * x
                if v > n:
                    break
                ret[v] += 1
    return ret[1:]
```

- [submitted #15159332 - Acing Programming Contest 2020](https://atcoder.jp/contests/aising2020/submissions/15159332)
- ![image](https://gyazo.com/428c4eee4eb087c1349756bdb8805ce7/thumb/1000)
    - Whoa, that's the code for the highest speed on PyPy submitted during the contest, I wonder if there's some kind of achievement release?

[D - Anything Goes to Zero](https://atcoder.jp/contests/aising2020/tasks/aising2020_d)
![image](https://gyazo.com/7a40546dbd35aecf59693a91c166bcd3/thumb/1000)
- 200,000 binary digits are passed.
    - So to treat it as a number is reckless.
- I implemented the function in question naively and observed the values after one step, and they are all pretty small!
    - Simple implementation = count the number of 1's in a binary string of numbers
python

```
def f(n):
    p = bin(n).count("1")
    return n % p
```

:

```
>>> [f(x) for x in range(1, 19)]
[0, 0, 1, 0, 1, 0, 1, 0, 1, 0, 2, 0, 1, 2, 3, 0, 1, 0]
```

- We take the surplus in popcount, so it gets very small very quickly.
- If a binary number with 200,000 digits is passed, one conversion will result in a maximum of 200,000.
    - It's about 16 digits, so one more step of calculation will arrive at the table above.
- In other words, we can lightly find the value after one step of 200,000 binary digits.
    - With respect to this "lightening up", if we take the problem condition naively, we need to calculate the remainder for each digit bit-reversed value of a 200,000-digit binary number, which is obviously no good.
    - Then, the calculation of the remainder for 200,000 values is made in constant order by finding the "remainder to the power of two" in advance.
    - I wrote it naively without this speedup first and ran it through the test.
        - I submitted it and it went RE.
        - If an input has only one bit standing and that bit is inverted, it is 0 from the beginning.
        - If you try to calculate the remainder without realizing it, you get zero division because popcount is also zero.
    - I tested that the remainder in the naive solution method and the remainder in the fast solution method match and then replaced them (the part I commented out in the middle).
- It may seem slow to count the number of 1's in a binary string of numbers, but the whole thing was 205 msec, and it was on a page from the fastest to the slowest.
    - It doesn't make sense to speed up code that doesn't account for a large percentage of execution time, so we're cutting corners.
python

```
def solve(N, X):
    o1 = ord("1")

    def f(n):
        p = bin(n).count("1")
        return n % p

    table = [0] * 20
    for i in range(1, 20):
        x = f(i)
        if x == 0:
            table[i] = 1
        else:
            table[i] = table[x] + 1

    numOne = X.count(o1)
    ret = [0] * N

    v = 0
    mod = numOne + 1
    p2mod_p1 = [0] * N
    p = 1
    for j in range(N):
        v *= 2
        v %= mod
        if (X[j] == o1):
            v += 1
        p2mod_p1[j] = p
        p *= 2
        p %= mod

    xmod_p1 = v % mod  # X mod (bc(X) + 1)
    xmod_m1 = 0  # X mod (bc(X) - 1)
    if numOne > 1:
        p = 1
        p2mod_m1 = [0] * N
        v = 0
        mod = numOne - 1
        for j in range(N):
            v *= 2
            v %= mod
            if (X[j] == o1):
                v += 1
            xmod_m1 = v % mod
            p2mod_m1[j] = p
            p *= 2
            p %= mod

    for i in range(N):
        if X[i] == o1:
            mod = numOne - 1
            if mod == 0:
                # already 0
                ret[i] = 0
                continue
            v2 = (xmod_m1 - p2mod_m1[-1-i]) % mod
        else:
            mod = numOne + 1
            v2 = (xmod_p1 + p2mod_p1[-1-i]) % mod
        # v = 0
        # for j in range(N):
        #     v *= 2
        #     v %= mod
        #     if (X[j] == o1) ^ (i == j):
        #         v += 1
        # v %= mod
        # debug(": v, v2", v, v2)
        # assert v == v2
        v = v2

        if v == 0:
            ret[i] = 1
            continue
        if v < 20:
            ret[i] = table[v] + 1
            continue

        v = f(v)
        ret[i] = table[v] + 2

    return ret
```

[submitted #15172307 - Acing Programming Contest 2020](https://atcoder.jp/contests/aising2020/submissions/15172307)

Thoughts on problems not solved
- When D was finished, there were 35 minutes left, and I felt like giving up (I'm beating myself up), thinking that there was a good chance I wouldn't be able to solve it, considering my usual pace.
- Sort by the K value of how many camels want to be in the first group or not in the first group" in order, with the size of the first group as the definition area, DP...
    - This DP, the square order, is a TLE because it is a TLE...
- I'll do a simple DP for now (15 minutes left).
    - Test case 1 passes, but the rest fail.
    - Even if you fix this bug, the TLE issue...
- I was looking at why it was fading, and finally realized with about 6 minutes left that some camels like to be behind.
    - If we judge in order of decreasing K, the timing of judgment of "a camel that is very happy only at the very back" will be delayed and will not be the optimal solution.
- Give up and look at F (3 minutes left)
    - Wouldn't this be easier?
        - → It wasn't easy.
    - I don't know if it's really easy or not because I didn't solve it, but maybe I should have looked at both problems with 35 minutes left.
    - →If the sum of the two values is determined, then the formula [[Exchange of product and sum]] can be used to obtain the value from that point forward.
        - I couldn't figure out how to multiply them in combination, but I thought it looked like [[formal power series]], and that's exactly how maspy solved it.
- The Good
    - As I've written "naively" several times, I took the approach of writing naively first and then speeding it up.
    - I think this is good.

---
This page is auto-translated from [/nishio/エイシング プログラミング コンテスト 2020](https://scrapbox.io/nishio/エイシング プログラミング コンテスト 2020) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "keyence2021"
---

[Keyence Programming Contest 2021 - AtCoder](https://atcoder.jp/contests/keyence2021) ARC equivalent difficulty
It was three questions, A-C.

![image](https://gyazo.com/1cf13ccfd7b034a59134adbb8aa0b42a/thumb/1000)


[A - Two Sequences 2](https://atcoder.jp/contests/keyence2021/tasks/keyence2021_a)
![image](https://gyazo.com/8886c1232049da6b710c42699eb6acb4/thumb/1000)
- $c_n = \max a_ib_j[iɛle jɛle n$] problem ([[Iverson bracket]] notation)
- $c_n = \max (c_{n-1},  \max a_ib_n [i\le n])$
- $c_n = \max (c_{n-1},  b_n \max a_i [i\le n])$
- So, we can save $\max a_i [iɛle n$] separately
python

```
def main():
    N = int(input())
    AS = list(map(int, input().split()))
    BS = list(map(int, input().split()))
    maxAS = []
    x = 0
    for i in range(N):
        x = max(x, AS[i])
        maxAS.append(x)

    ret = AS[0] * BS[0]
    print(ret)
    for i in range(1, N):
        ret = max(ret, maxAS[i] * BS[i])
        print(ret)
```


[B - Mex Boxes](https://atcoder.jp/contests/keyence2021/tasks/keyence2021_b)
![image](https://gyazo.com/399ab72dbb56393a66ef66e1ef97034c/thumb/1000)
- There is no benefit to putting the same value in the same box.
- If the numbers are flying, it doesn't affect the results.
- Therefore, the greedy method where the optimal solution is to "put in as much as you can in consecutive order starting from 0
- I forgot the limit on the number of boxes and got WA once: `K > 0` in (1)
python

```
def main():
    N, K = map(int, input().split())
    AS = list(map(int, input().split()))
    from collections import Counter
    count = Counter(AS)
    ret = 0
    while count[0] > 0 and K > 0:  # (1)
        i = 0
        K -= 1
        while count[i] > 0:
            ret += 1
            count[i] -= 1
            i += 1

    print(ret)
```


[C - Robot on Grid](https://atcoder.jp/contests/keyence2021/tasks/keyence2021_c)
![image](https://gyazo.com/e60412189e8d57b2f1c1e23ba8897f9c/thumb/1000)
- At first, I did the DP on the wrong side of the diagram and had trouble getting the sample to fit.
    - ![image](https://gyazo.com/d77469b7257adfbca3f257a13f5e8b0e/thumb/1000)
    - For example, a path that does not pass through * is given as 1 in the final answer in the above DP, but if there are M *s, it is correct that it should be 3^M.
    - I also made a mistake once as to what I should divide the final result by to make it add up, but the sample is kind enough to look at it carefully.
        - In sample 1, there are two transitions to the goal and one *, so divide by 3^1 because it is one extra transition.
        - In sample 2, there are 4 transitions and 4 *'s, so divide by 3^0
    - RE is out because I forgot that you can put negative values in pow since Python 3.8. see [[Inverse Element in mod P]].
    - I was using a dictionary with tuples as keys and TLE'd it, so I changed it to an array.
        - W+2 is a combination of 1-origin and 1-square expansion to avoid conditional branching at the edge.
python

```
def main():
    MOD = 998_244_353
    H, W, K = map(int, input().split())
    CS = [0] * ((H + 2) * (W + 2))
    for _k in range(K):
        h, w, c = input().strip().split()
        CS[(int(h) * (W + 2) + int(w))] = ord(c)

    table = [0] * ((H + 2) * (W + 2))
    v = table[1 + (W + 2)] = 1
    for h in range(1, H + 1):
        for w in range(1, W + 1):
            pos = h * (W + 2) + w
            v = table[pos] % MOD
            c = CS[pos]
            if c == 88:  # "X":
                table[pos + 1] += v * 3
                table[pos + (W + 2)] += v * 3
            elif c == 68:  # "D":
                table[pos + (W + 2)] += v * 3
            elif c == 82:  # "R":
                table[pos + 1] += v * 3
            else:
                table[pos + 1] += v * 2
                table[pos + (W + 2)] += v * 2

    ret = table[H * (W + 2) + W] % MOD
    LEN = (H + W - 2)
    NEGK = H * W - K
    ret *= pow(3, (MOD - 1 - (LEN - NEGK)), MOD)
    ret %= MOD
    print(ret)
```


[D - Choosing Up Sides](https://atcoder.jp/contests/keyence2021/tasks/keyence2021_d)
- ![image](https://gyazo.com/b2e3f90a7532cacff62fc8ed74d62a72/thumb/1000)

- Thoughts.
    - When 8 people are divided in half to play against each other, there are 3 people who will be on the same team as the number 1 person, and the "number of times they were the same" of those people will increase by 1, so everyone except the number 1 person will have the same "number of times they were on the same team as the number 1 person": 3 x 7 times 21
        - Mistake.
            - We only need to add seven vectors such that three of the seven locations are 1's and all of them are 3's
- Twitter after the end
        - [[dual vector]]  [src](https://twitter.com/ngtkana/status/1350449811309305856?s=21)
    - Roughly the same problem as when N=M in [E - Odd Sum Rectangles](https://atcoder.jp/contests/hitachi2020/tasks/hitachi2020_e) [src [https://twitter.com/titia_til/](https://twitter.com/titia_til/) status/1350443154089025537]
    - Recursion [src](https://twitter.com/SSRS_cp/status/1350442817785479170)
        - [[Adamar procession]]  [src](https://twitter.com/nullkara/status/1350470699400400896?s=21) [src](https://twitter.com/kyopro_friends/status/1350449299272790017?s=21)
    - D: If N = 3, create 11110000 11001100 10101010 and select one or more of these xor [src](https://twitter.com/poyothon/status/1350443900259876870)
        - I see
        - You can create N different sequences of the same value such that [$ 2^i (0 \le i < N)
        - There are $2^N$ XORs of these values, each of which may or may not be selected, and all but 00000000 have four 1's ($2^{N-1}$).
        - This set is closed for XOR (0 is the unit source)
        - Since "the number of times they were on the same team" is "the number of digits that are 0 in the XORed value," this property is convenient because the number of digits that are 0 does not change when XORing different ones.
- Post-contest implementation
    - Make N ways such that the same sequence of values is [$ 2^i (0 \le i < N)
        - Python can also perform bitwise operations on 256-bit integers without any problem.
    - Enumerate the values created by XORing these N
        - Bitwise enumeration of subsets, a commonly used method
    - String binary numbers, replacing 0s and 1s with A and B
- AC
python

```
def main():
    N = int(input())
    group = []
    for i in range(N):
        P = 2 ** (2 ** i)
        group = [x * (P + 1) for x in group]
        group.append(P - 1)

    K = 2 ** N - 1
    print(K)
    for i in range(1, K + 1):
        x = 0
        for j in range(N):
            if (1 << j) & i:
                x = x ^ group[j]
        s = f"{x:0256b}"[-(2 ** N):]
        s = s.replace("0", "A").replace("1", "B")
        print(s)
```

- [Adamar procession - Wikipedia](https://ja.wikipedia.org/wiki/%E3%82%A2%E3%83%80%E3%83%9E%E3%83%BC%E3%83%AB%E8%A1%8C%E5%88%97)
    - I see
    - ${\displaystyle {\boldsymbol {H}}^{\intercal }{\boldsymbol {H}}=n{\boldsymbol {I}}_{n}}$] which means that for $i \neq j$ $\sum_k H_{ik}H_{kj} = 0$ which means that
        - Therefore, the problem condition "the number of times they were on the same team is equal for any i<j" is satisfied.
    - I didn't notice the recursive construction [$ \begin{bmatrix} H & H\ H & -H\end{bmatrix}
    - I did a quasi-isomorphism of the group ${\displaystyle \{1,-1,\times \}\mapsto \{0,1,\oplus \}}$ and then ${\displaystyle {\boldsymbol {F}}_{n}={\begin{bmatrix}0_{1\ times 2^{n-1}}&1_{1\times 2^{n-1}}\{\boldsymbol {F}}_{n-1}&{\boldsymbol {F}}_{n-1}\end{bmatrix}}}$
        - $0_{1\times 2^{n-1}} 1_{1\times 2^{n-1}}$ is P - 1
        - ${\boldsymbol {F}}_{n-1} {\boldsymbol {F}}_{n-1}$ is `group = [x * (P + 1) for x in group]`
    - I then XORed each subset, but ${\displaystyle {\boldsymbol {H}}_{2^{n}}={\boldsymbol {F}}_{n}^{\intercal }{\boldsymbol {F}}_{n}}$ is also ok
        - F has n rows and 2^n columns, each column is different, so there are n-bit integers all the way through
            - Order doesn't mean anything.
        - $H_{ij} = \sum_k F_{ki}F_{kj}$, so this is in essence popcount(i & j) mod 2
            - It comes down to the construction with the following popcount
- Official Explanation
    - I'm building it using popcount(i & j).
    - This is because in the recursive construction of the Adamar matrix, we're only sign-reversing if the most significant bits of i & j are 1.
        - ![image](https://gyazo.com/5c9aa6ca4a24a6d8af633a07ebb33cf5/thumb/1000)
    - popcount(i & j) becomes the number of times the ij element is sign-reversed

---
This page is auto-translated from [/nishio/keyence2021](https://scrapbox.io/nishio/keyence2021) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
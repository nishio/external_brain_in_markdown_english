---
title: "DP T"
---

[T - Permutation](https://atcoder.jp/contests/dp/tasks/dp_t)
- Counting up how many ways there are to arrange numbers to satisfy a given size relationship
- Is it a DP that takes "the set of numbers we haven't used yet" as its domain?
    - Impossible because the size of the set is 3000 and large.
- Can we narrow the definitional range by equating something with something else?
    - ![image](https://gyazo.com/cf77e332e55be1555ffab63ac2e210de/thumb/1000)
    - There are still "three options" in either of these two situations.
    - So, "how many are greater than or less than the number selected immediately before" is the domain of definition
- Where is the end of the search?
    - With one number remaining.
    - DP that enumerates "1 remaining state" in advance and then finds "k remaining states using the values of k-1 remaining states".


![image](https://gyazo.com/15d46557ea961335ad637bf01a487a4a/thumb/1000)

First, make the code work correctly when N=2.
python

```
def solve(N, lessthan):
    # init
    # f("<", lower=0, upper=1) = 1, f("<", 1, 0) = 0
    k = 1
    table = [0] * (k + 1)
    if lessthan[-1]:
        for i in range(k + 1):
            table[i] = k - i
    else:
        for i in range(k + 1):
            table[i] = i

    return sum(table)
```


Then make the code work correctly when N=3
python

```
def solve(N, lessthan):
    k = 1
    table = [0] * (k + 1)
    if lessthan[-1]:
        for i in range(k + 1):
            table[i] = k - i
    else:
        for i in range(k + 1):
            table[i] = i

    if N > 2:
        k = 2
        newtable = [0] * (k + 1)
        if lessthan[-2]:
            for i in range(k + 1):
                for j in range(k - i):
                    newtable[i] += table[j + i]
        else:
            for i in range(k + 1):
                for j in range(i):
                    newtable[i] += table[j]
        table = newtable
    return sum(table)
```


Then extend to general N.
- Now all the sample code goes through.
- TLE when submitting
python

```
def solve(N, lessthan):
    k = 1
    table = [0] * (k + 1)
    if lessthan[-1]:
        for i in range(k + 1):
            table[i] = k - i
    else:
        for i in range(k + 1):
            table[i] = i

    for k in range(2, N):
        newtable = [0] * (k + 1)
        if lessthan[-k]:
            for i in range(k + 1):
                for j in range(k - i):
                    newtable[i] += table[j + i]
        else:
            for i in range(k + 1):
                for j in range(i):
                    newtable[i] += table[j]
        table = [x % MOD for x in newtable]
    return sum(table) % MOD
```


Since the loop is a range sum, we can use cumulative summing to speed up the process.
python

```
    for k in range(2, N):
        newtable = [0] * (k + 1)
        acc = [0] + list(accumulate(table))
        if lessthan[-k]:
            for i in range(k + 1):
                # for j in range(k - i):
                #    newtable[i] += table[j + i]
                newtable[i] += acc[k] - acc[i]
        else:
            for i in range(k + 1):
                # for j in range(i):
                #    newtable[i] += table[j]
                newtable[i] += acc[i]
        table = [x % MOD for x in newtable]
```

AC: [https://atcoder.jp/contests/dp/submissions/15098388](https://atcoder.jp/contests/dp/submissions/15098388)

---
This page is auto-translated from [/nishio/DP T](https://scrapbox.io/nishio/DP T) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "ABC178F"
---

[F - Contrast](https://atcoder.jp/contests/abc178/tasks/abc178_f)
![image](https://gyazo.com/2f42a5744a2fdfabc0c5a486a12710fd/thumb/1000)

from [[ABC178]]
ABC178F
- real time
    - Why don't we just use it from the most surplus number, and implement it?
        - 24 WA
    - Check later to see if the policy was not good enough.
- Official Explanation
    - The solution is obtained by shifting the range so that they do not overlap.
- Putting aside time to think about it
        - [[Build one, problem.]]
    - Need to find one of the many solutions that is easy to construct.
        - [[Greed Law Proof Patterns]]
        - If there is a solution, then there is a solution of this form."
    - First, we look at the number with the highest number of occurrences.
        - ![image](https://gyazo.com/5e927d1680578778fb5d07f47a5bc7a3/thumb/1000)
        - A: Obviously impossible if the number of occurrences C exceeds N
        - B: Just when N, you have to put them in so they don't overlap.
            - At this point, it doesn't matter what the sequence of the remaining squares is.
        - C: Otherwise, just line up the N-C squares so that they are not covered
            - Can be placed as long as there is no number of N appearances.
                - The condition "choose the number with the greatest frequency of occurrence" indicates that there is no such thing
- mounting
    - 20 minutes to implement, 25 minutes to fix bugs on hand, submit and 20WA.
        - Hmmm, what pattern am I missing?
        - →continue when the pointer is incremented even though it is a for statement.
    - Random test found strange output, corrected and submitted in 53 minutes, 6WA
            - [[Gaining Information from Judge Results]]
python

```
assert Counter(BS) == Counter(ret)
return ret
```

        - 6WA
python

```
assert all(AS[i] != ret[i] for i in range(N))
```

        - 6WA?
python

```
assert len(ret) == N
```

        - Mmm? Is this another 6WA?
        - Oh, I see,
python

```
assert 1 == 2
print("No")
```

        - 16RE
        - In other words, there are cases where they are returning a No when they really shouldn't.
python

```
if b_count[b] == 0:
    assert 1 == 2
    return
```

        - 6RE
        - So this is a mistake.
- →AC
python

```
def solve(N, AS, BS):
    from collections import Counter
    a_count = Counter(AS)
    b_count = Counter(BS)

    max_occur = 0
    when_max = None
    for i in range(N + 10):
        t = a_count[i] + b_count[i]
        if t > N:
            return
        if t > max_occur:
            max_occur = t
            when_max = i

    ret = []
    del a_count[when_max]
    del b_count[when_max]
    a_keys = list(a_count.keys())
    b_keys = list(b_count.keys())
    a_pointer = 0
    b_pointer = 0
    a_len = len(a_keys)
    b_len = len(b_keys)
    for _i in range(N - max_occur):
        a = a_keys[a_pointer]
        if a == when_max:
            a_pointer = (a_pointer + 1) % a_len
            a = a_keys[a_pointer]
        c = a_count[a]
        if c == 0:
            del a_count[a]
            a_pointer = (a_pointer + 1) % a_len
            a = a_keys[a_pointer]

        b = b_keys[b_pointer]
        while a == b or b == when_max or b_count[b] == 0:
            b_pointer = (b_pointer + 1) % b_len
            b = b_keys[b_pointer]

        ret.append((a, b))
        a_count[a] -= 1
        b_count[b] -= 1

    for b in b_count:
        for _i in range(b_count[b]):
            ret.append((when_max, b))
    for a in a_count:
        for _i in range(a_count[a]):
            ret.append((a, when_max))

    ret.sort()
    ret = [b for a, b in ret]
    return ret
```



---
This page is auto-translated from [/nishio/ABC178F](https://scrapbox.io/nishio/ABC178F) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
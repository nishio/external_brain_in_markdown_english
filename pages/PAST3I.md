---
title: "PAST3I"
---

from  [[Third Algorithm Practical Skills Test]]
PAST3I
- The problem is to repeatedly execute commands such as transpose, row swap, column swap, display the value of a particular square, etc. on a square matrix.
- Under the problem conditions, the maximum size of the matrix is 100,000, so we can see that naively having a matrix is not a viable option.
- The first algorithm I thought of was "If you follow the time axis in reverse order from the display order, it is easy because you only have to think about one square.
    - However, after exceeding the time limit, he realizes that this is not good enough.
    - It was a simple enough program, and I realized that speeding it up with the algorithm as it was would not solve the problem.
- It probably means "when the longest command sequence is 100,000 and about half of them are display commands, it takes about 1.2 billion steps".
    - With that in mind, we added that to the test case.
- We will have the matrix broken down into the information "which row or column is the current row or column originally".
        - [[Transposition is a 1-bit flag]] is all that is needed.
python

```
if 1:
    N = int(input())
    Q = int(input())
    queries = []
    for i in range(Q):
        queries.append([int(x) for x in input().split()])
else:
    N = 100000
    queries = [
        [2, 1, 2],
        [4, 1, 2]
    ] * 10000
    queries.append([4, 1, 2])
    Q = len(queries)


isTransposed = False
xs = list(range(N + 1))
ys = list(range(N + 1))

for q in queries:
    f = q[0]
    if f == 4:
        i, j = q[1:]
        if isTransposed:
            i, j = j, i
        print(N * (xs[i] - 1) + ys[j] - 1)
    elif f == 3:
        isTransposed = not isTransposed
    else:
        i, j = q[1:]
        if (f == 1) ^ isTransposed:
            xs[i], xs[j] = xs[j], xs[i]
        else:
            ys[i], ys[j] = ys[j], ys[i]
```


---
This page is auto-translated from [/nishio/PAST3I](https://scrapbox.io/nishio/PAST3I) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
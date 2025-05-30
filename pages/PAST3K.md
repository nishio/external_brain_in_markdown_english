---
title: "PAST3K"
---

from  [[Third Algorithm Practical Skills Test]]
PAST3K
- A problem where there are multiple boxes with multiple numbers on multiple desks and you have to move them here and there according to the commands.
- There are 200,000 desks, 200,000 boxes, and 200,000 orders.
    - If the execution of a single instruction is not light enough, the time will be exceeded.
- Using Python lists in an array-like fashion to create a list of data structure meanings.  [[linked list]].
    - This is because I was afraid of running out of time due to overhead if I did it normally with objects and references, and also because I thought it was just a difference in the appearance of the code and not essentially the same.
    - We have four arrays of length N+1, meaning "the bottom box of box i", "the top box of box i", "the bottom box of desk i", and "the top box of desk i", respectively.
    - N+1 because the problem condition is 1-origin.
        - We created a situation where we could use it without worrying about it rather than inputting and outputting one shift without making a mistake.
        - And I can use 0 to mean null.
        - Problem E didn't do that, so it needs to be displaced in four places.
- Prepare a function that displays a clear indication for debugging purposes, and implement the rest in a straightforward manner.

python

```
N, Q = [int(x) for x in input().split()]

prev = [-table for table in range(N + 1)]
next = [0] * (N + 1)
top = [table for table in range(N + 1)]
bottom = [table for table in range(N + 1)]


def debugPrint():
    blocks = [[] for i in range(N + 1)]
    for table in range(1, N + 1):
        cur = bottom[table]
        while cur:
            blocks[table].append(cur)
            cur = next[cur]

    print(blocks[1:])


for table in range(Q):
    frm, to, x = [int(x) for x in input().split()]
    # print(frm, to, x)

    p = prev[x]
    if p > 0:
        next[p] = 0
        if top[to]:
            prev[x] = top[to]
            next[top[to]] = x
        else:
            # x is first block of TO
            prev[x] = -to
            bottom[to] = x

        top[to] = top[frm]
        top[frm] = p
    else:
        # x is last block
        bottom[frm] = 0
        if top[to]:
            prev[x] = top[to]
            next[top[to]] = x
        else:
            # x is first block of TO
            bottom[to] = x
            top[to] = top[frm]
            prev[x] = -to

        top[to] = top[frm]
        top[frm] = 0

    # print(prev)
    # print(next)
    # print(top)
    # print(bottom)
    # debugPrint()
    # print()


pos = [0] * (N + 1)
for table in range(1, N + 1):
    cur = bottom[table]
    while cur:
        pos[cur] = table
        cur = next[cur]

for i in range(1, N + 1):
    print(pos[i])
```


Reading other people's code, it seems that this doesn't need to be a two-way list here, just a list of the top of the desk and the bottom of the box
- [https://atcoder.jp/contests/past202005-open/submissions/14109675](https://atcoder.jp/contests/past202005-open/submissions/14109675)

---
This page is auto-translated from [/nishio/PAST3K](https://scrapbox.io/nishio/PAST3K) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
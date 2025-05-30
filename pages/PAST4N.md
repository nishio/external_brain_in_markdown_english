---
title: "PAST4N"
---

from  [[Fourth Algorithm Practical Skills Test]]
PAST4N

[N - Fill in the Mass](https://atcoder.jp/contests/past202010-open/tasks/past202010_n)
![image](https://gyazo.com/68a9ca92e218c196afc3b9fe1065c77f/thumb/1000)

- Thoughts.
    - `? Number of ways to fill in the number of ways that are all median around the`
    - `? It's tricky to influence each other`
    - There's such a thing as all hatchets.
        - DP?
        - 18 rows and 6 columns of squares
        - DPs that are OK once the 6-row pattern is determined.
    - NG only when the three surroundings have the same value.
    - Need a 6 column pattern as well as how many 1s are around the top square?
        - When the top is 1,0,0 and the bottom is 1, don't put a 0 on the bottom.
        - 2 bits are needed if you include the critical 0,1
    - No, no, no, no.
        - A 0 placed next to it can become a dangerous 0 later.
- Official Explanation
    - DP in two rows
        - [[Notice the small constants.]], 6 means you can double the bit DP.
    - I guess I made the information I brought around too small, or I should have thought about it from the larger side.
        - If we can get all the information on the line above, that's enough to identify the current line.
        - Then how far do we need to go?
        - Three up is not necessary.
        - Therefore, DP in 2 lines
        - I guess I should have thought of it in that vein...
- think again
    - Pack 2 rows of information into 2^12 and shift 6 bits for each row forward
    - The given hint data is bit masked and the discrepancy is done by bitwise operations.
        - The fact that there is a 1 in every place where there should be a 1 can be checked by ANDing the mask and checking if it is identical to the mask.
        - To see if there is a 0 where there should be a 0, just or the reverse mask.
    - I guess we'll just have to find out naively that it's the median of the surrounding area.
        - And it's tricky because of the edges.
        - I reread the problem statement and the ends were treated as zeroes.
        - 1 is valid if the value obtained by adding the four surrounding values is greater than or equal to 2, 0 is valid if the value is less than or equal to 2, and both are valid if the value is 2.
- 5AC 14WA It looks like no TLE for now.
    - Including the sample, it's 8AC, so it doesn't sound like it's fundamentally wrong.
    - What's funny...
python

```
def solve(data):
    ZERO = ord("0")
    ONE = ord("1")

    onemasks = []
    zeromasks = []
    for y in range(18):
        onemask = 0
        zeromask = 0
        for i in range(6):
            if data[y][i] == ONE:
                onemask += 1 << i
            if data[y][i] != ZERO:
                zeromask += 1 << i
        onemasks.append(onemask)
        zeromasks.append(zeromask)

    def is_valid(y, s):
        return (
            onemasks[y] & s == onemasks[y] and
            zeromasks[y] | s == zeromasks[y]
        )

    def is_median(p1, p2, s):
        for i in range(6):
            # median check
            mask = (1 << i)
            neighbor = sum(
                x & mask > 0 for x in
                [p1, (p2 << 1), (p2 >> 1), s])
            is_ok_one = (p2 & mask) and neighbor >= 2
            is_ok_zero = not(p2 & mask) and neighbor <= 2
            if not (is_ok_one or is_ok_zero):
                return False
        return True

    def debugprint(*args):
        def to_s(x):
            return "".join(reversed(f"{x:06b}"))
        print(*[to_s(x) for x in args], sep="\n", file=sys.stderr)

    P6 = 2 ** 6
    P12 = 2 ** 12
    table = [0] * P12
    for s in range(P6):
        if is_valid(0, s):
            for s2 in range(P6):
                if is_valid(1, s) and is_median(0, s, s2):
                    table[s * P6 + s2] = 1

    for y in range(2, 18):
        newtable = [0] * P12
        for s in range(P6):
            if not is_valid(y, s):
                continue
            for past in range(P12):
                if table[past] == 0:
                    continue
                p1, p2 = divmod(past, P6)
                if is_median(p1, p2, s):
                    newtable[p2 * P6 + s] += table[past]
        table = newtable
    return sum(table)
```



---
This page is auto-translated from [/nishio/PAST4N](https://scrapbox.io/nishio/PAST4N) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
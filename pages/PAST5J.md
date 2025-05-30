---
title: "PAST5J"
---

[J - long long string](https://atcoder.jp/contests/past202012-open/tasks/past202012_j)
![image](https://gyazo.com/a30032ca3d2b05fc4156aed0ed48365c/thumb/1000)
- Initial Considerations
    - No naive output.
    - If we pre-calculate the size of the block for each iteration, we can solve the problem by gradually taking the value of the query as a remainder.
    - Consideration complete
- production run
    - It's confusing when it should have been implemented calmly.
        - After solving one misalignment bug, the sample finally went through after 56 minutes.
        - However, TLE
        - I used to cut out the string that would be the unit of repetition, but I figure I can just wait and see where it starts in the original string.
        - Plus, we'll use 16 minutes and have another TLE, or even an MLE for that matter.
        - What does that mean?
        - For example, when there are a lot of 9s going on, the "size of the repeating block" becomes a very large number, the problem is that I was not aware of this and just did it.
        - In real time, I thought, "Does that mean the policy was totally wrong?" And I gave up.
            - When I woke up after a night's sleep, I realized that the number passed as a query is limited to less than 10^15, so I can terminate the string parsing process when it exceeds that number.
- Re-implementation after contest
    - The appearance of the number 1 means "the description to that point is repeated twice".
    - You can think of it as having a zero at the end. [[sentry]]
    - A block can be defined as consisting of "no more than one block," "zero or more than one letter of the alphabet," and "one number.
    - One of the causes of confusion, giving an appropriate name to a concept before it is clearly separated, and then being drawn to the name distorts the perception of the concept.
    - ![image](https://gyazo.com/ce5657a86b818f20d5d59560de74b9ef/thumb/1000)
    - The production confused BLOCK and UNIT.
    - blocklen(i + 1) = (blocklen(i) + taillen(i + 1)) * repeat(i + 1)
    - Flow after parsing
        - Set X to 0-origin
        - This is a repeated string of unit(-1), so take too much
- AC
python

```
def solve(S, X):
    X -= 1  # 1-origin to 0-origin
    S += "0"
    blocklen = [0]
    unitlen = [0]
    repeat = [0]
    tailstart = [0]
    taillen = [0]
    tlen = 0
    tstart = 0
    for i, c in enumerate(S):
        if c in "0123456789":
            rep = int(c) + 1
            repeat.append(rep)
            tailstart.append(tstart)
            taillen.append(tlen)
            unitlen.append(blocklen[-1] + tlen)
            blocklen.append(unitlen[-1] * rep)
            if blocklen[-1] > X:
                break
            # next tail
            tstart = i + 1
            tlen = 0
        else:
            tlen += 1

    for i in reversed(range(len(blocklen))):
        X %= unitlen[i]
        if X >= blocklen[i - 1]:
            X -= blocklen[i - 1]
            return S[tailstart[i] + X]
```




[PAST #5 J - Long, long strings - Ebichan's Diary](https://rsk0315.hatenablog.com/entry/2020/12/29/162310)

---
This page is auto-translated from [/nishio/PAST5J](https://scrapbox.io/nishio/PAST5J) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
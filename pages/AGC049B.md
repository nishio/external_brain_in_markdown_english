---
title: "AGC049B"
---

[B - Flip Digits](https://atcoder.jp/contests/agc049/tasks/agc049_b)
![image](https://gyazo.com/9ba0804fe68f50c3755d1445acfb90cb/thumb/1000)

from [[AGC049]]
AGC049B
- Thoughts.
    - The operation to be performed is either 01 to 10 or 11 to 00
    - Thinking from behind
        - ![image](https://gyazo.com/cf7f0cc4abb2a7ed8bb21c47b8a9a937/thumb/1000)
        - In case 1, trailing 1s are bears.
            - Because it can't disappear.
        - Can I turn it off in case 2?
        - DP by the number of times it can be deleted?
            - N=10^5, so it's hard when you can delete about 10^4
        - In case 2, can I turn it off? →No, not good.
            - S: 110011
            - T: 001100
            - At this time, if the back is erased first, it becomes unattainable.
            - Do you want to do it before?
    - I've been doing this for a while.
        - ![image](https://gyazo.com/df77fbc848e01430899c56bdbd3d99ff/thumb/1000)
            - [[Greed Law Proof Patterns]]
        - If the pattern to be deleted is in the optimal solution, it contradicts the assumption that it is the optimal solution because a better solution can be created by exchanging the places to be deleted, and therefore there is no pattern to be deleted
        - AC

    - Tweet:
        - The operation is to move one 1 to the left or erase 2 pieces.
        - When we focus on the leftmost 1 and S is to the left, we add the cost of erasing the 1 to the answer to make the 1 we focus on two ahead, because if there is a solution, that 1 must disappear.
        - In the reverse case, the first 1 is not eliminated in the optimal solution because eliminating the first 1 is a loss.
            - Add the cost of moving the first 1 in S to the first 1 in T to the answer and focus on the next 1, respectively.
        - When you reach the end, it is the best solution and you return the answer.
        - If an inconsistency occurs, such as a missing S, we know that a solution does not exist.
        - My implementation enumerates where one stands first, but this may be solved without doing so.
            - The code is easy to understand because "look out for the next one" is a subscript increment.
python

```
def solve(N, S, T):
    spos = []
    tpos = []
    diff = 0
    for i in range(N):
        if S[i] == 1:
            spos.append(i)
            diff += 1
        if T[i] == 1:
            tpos.append(i)
            diff -= 1

    if diff % 2 == 1:
        return -1
    if diff < 0:
        return -1

    tpos += [N] * N
    spos.append(-1)
    i = 0
    j = 0
    ret = 0
    while i < len(spos) - 1:
        if spos[i] < tpos[j]:
            # spos_i should be deleted
            next = spos[i + 1]
            if next == -1:
                return -1
            ret += (next - spos[i])
            i += 2
            continue

        ret += (spos[i] - tpos[j])
        i += 1
        j += 1
    if j != len(tpos) - N:
        return -1
    return ret
```


---
This page is auto-translated from [/nishio/AGC049B](https://scrapbox.io/nishio/AGC049B) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
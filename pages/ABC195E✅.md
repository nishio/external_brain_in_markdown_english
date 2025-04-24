---
title: "ABC195E✅"
---

from [[ABC195]]
ABC195E
    - [[Working backwards from the goal]]
- I can't think of much to write because I wrote it honestly, passed the test at hand in one shot, and submitted it AC.
py

```
def main():
    N = int(input())
    SS = input().strip().decode('ascii')
    XS = input().strip().decode('ascii')

    goal = [0] * 7
    goal[0] = 1  # if 1 Taka win

    for i in reversed(range(N)):
        s = int(SS[i])
        prev_goal = []
        if XS[i] == "A":
            for prev in range(7):
                if goal[(prev * 10 + s) % 7] == 0 or goal[(prev * 10) % 7] == 0:
                    prev_goal.append(0)
                else:
                    prev_goal.append(1)
        else:  # "T" 
            for prev in range(7):
                if goal[(prev * 10 + s) % 7] == 1 or goal[(prev * 10) % 7] == 1:
                    prev_goal.append(1)
                else:
                    prev_goal.append(0)
        goal = prev_goal

    if goal[0] == 1:
        print("Takahashi")
    else:
        print("Aoki")
```

- > E problem is an easy version of [[AGC045A]] "Xor Battle"! [tw](https://twitter.com/kyopro_friends/status/1370732280524599296)

---
This page is auto-translated from [/nishio/ABC195E✅](https://scrapbox.io/nishio/ABC195E✅) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "PAST4D"
---

from  [[Fourth Algorithm Practical Skills Test]]
PAST4D
[D - alter ego](https://atcoder.jp/contests/past202010-open/tasks/past202010_d)
- Thoughts.
    - Fill in the blanks from the end
    - If there's an empty space that's in contact with the edge, that length is the minimum required.
    - Count the number of blanks
    - Tip: If the longest blank is less than or equal to the sum of the blanks at both ends, then moving to fill in the blanks at both ends is sufficient.
- supplement
        - [[The order of operation is irrelevant.]]
- Official Explanation
    - 50 x 50 so you can explore the whole area.
python

```
def solve(N, S):
    spaces = []
    if S[0] == ord("#"):
        spaces.append(0)
        state = "BLOCK"
    else:
        state = "SPACE"
    c = 0

    for i in range(N):
        if state == "SPACE":
            if S[i] == ord("."):
                c += 1
            else:
                spaces.append(c)
                state = "BLOCK"
        else:
            if S[i] == ord("."):
                state = "SPACE"
                c = 1
            else:
                pass
    if state == "BLOCK":
        spaces.append(0)
    else:
        spaces.append(c)

    m = max(spaces)
    if m > spaces[0] + spaces[-1]:
        print(spaces[0], m - spaces[0])
    else:
        print(spaces[0], spaces[-1])
```


---
This page is auto-translated from [/nishio/PAST4D](https://scrapbox.io/nishio/PAST4D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
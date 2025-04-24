---
title: "PAST3D"
---

from  [[Third Algorithm Practical Skills Test]]
PAST3D
D The problem is to read the displayed values from the LED lighting information. It is guaranteed that nothing other than the pattern to be recognized will come in, so I made a list of patterns to be recognized and compared them with perfect matches. Of course, this list of patterns is used in the program, a quick transformation in Python's interactive console.
python

```
N = int(input())
S = [input(), input(), input(), input(), input()]

PATTERNS = """
####.##.##.####
.#.##..#..#.###
###..#####..###
###..####..####
#.##.####..#..#
####..###..####
####..####.####
###..#..#..#..#
####.#####.####
####.####..####
""".strip().split()

result = ""
for i in range(N):
    char = "".join(S[j][i * 4 + 1:i * 4 + 4] for j in range(5))
    result += str(PATTERNS.index(char))
print(result)
```


---
This page is auto-translated from [/nishio/PAST3D](https://scrapbox.io/nishio/PAST3D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
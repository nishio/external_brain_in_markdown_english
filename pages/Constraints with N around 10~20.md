---
title: "Constraints with N around 10~20"
---

:
| N | 10 | 11 | 12 | 13 | 14 | 15 | 16 | 17 | 18 | 19 | 20 |
| -- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- | -- |
| 2^N | 1e+03 | 2e+03 | 4e+03 | 8e+03 | 2e+04 | 3e+04 | 7e+04 | 1e+05 | 3e+05 | 5e+05 | 1e+06 |
| 3^N | 6e+04 | 2e+05 | 5e+05 | 2e+06 | 5e+06 | 1e+07 | 4e+07 | 1e+08 | 4e+08 | 1e+09 | 3e+09 |
| 4^N | 1e+06 | 4e+06 | 2e+07 | 7e+07 | 3e+08 | 1e+09 | 4e+09 | 2e+10 | 7e+10 | 3e+11 | 1e+12 |
| N 2^N | 1e+04 | 2e+04 | 5e+04 | 1e+05 | 2e+05 | 5e+05 | 1e+06 | 2e+06 | 5e+06 | 1e+07 | 2e+07 |
| N^2 2^N | 1e+05 | 2e+05 | 6e+05 | 1e+06 | 3e+06 | 7e+06 | 2e+07 | 4e+07 | 8e+07 | 2e+08 | 4e+08 |

- 3^N:  [[Sum of the number of subsets of a subset]]
- N 2^N:  [[number of colors]]

- [[Constraints on the number of vertices 18]]

python

```
print("N", *(n for n in range(10, 21)), sep="\t")

print("2^N", *(f"{2**n:.1g}" for n in range(10, 21)), sep="\t")
print("3^N", *(f"{3**n:.1g}" for n in range(10, 21)), sep="\t")
print("4^N", *(f"{4**n:.1g}" for n in range(10, 21)), sep="\t")
print("N 2^N", *(f"{n * 2**n:.1g}" for n in range(10, 21)), sep="\t")
print("N^2 2^N", *(f"{n ** 2 * 2**n:.1g}" for n in range(10, 21)), sep="\t")
```



---
This page is auto-translated from [/nishio/Nが10~20前後の制約](https://scrapbox.io/nishio/Nが10~20前後の制約) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
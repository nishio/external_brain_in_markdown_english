---
title: "ABC186D"
---

from [[ABC186]]
ABC186D
![image](https://gyazo.com/ea141db402b5efb6d1a5ec855b4fcfab/thumb/1000)
- ![image](https://gyazo.com/9ab4d650ada0faeb834057b1ca1f25ea/thumb/1000)
- [D - Sum of difference](https://atcoder.jp/contests/abc186/tasks/abc186_d)
- There is a lot of talk on Twitter about using cumulative sums, but I don't use cumulative sums.
- If you sort and take the difference between adjacent terms and let Di be the number of occurrences of Di in the solution is i(N-i), so just multiply and add.
    - ![image](https://gyazo.com/ea141db402b5efb6d1a5ec855b4fcfab/thumb/1000)
    - $S = \sum_{i=1}^{N-1} D_i i (N - i) = \sum_{i=0}^{N-2} D_i (i+1)(N-i-1)$
python

```
def main():
    N = int(input())
    AS = list(map(int, input().split()))
    AS.sort()
    DS = []
    for i in range(N - 1):
        DS.append(AS[i + 1] - AS[i])
    ret = 0
    for i in range(N - 1):
        ret += DS[i] * (N - 1 - i) * (i + 1)
    print(ret)
```

- By the way, I was on Twitter and saw a post that said, "Why should I sort?" There was a post that said
    - The value you're looking for is adding two unordered numbers for every combination that takes two out of N values.
    - ![image](https://gyazo.com/f2f8d759d6ee863c0e635f31664dabe5/thumb/1000)

    - No matter how you swap the order from symmetry to symmetry, the result remains the same.
    - So I went with "sorted" which is easier to handle.
    - [[Sort and remove absolute values.]]
    - [[Change the order of addition]]
    - [[Symmetrical, so you can reorder them.]]
        - [[The order is irrelevant.]]

---
This page is auto-translated from [/nishio/ABC186D](https://scrapbox.io/nishio/ABC186D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
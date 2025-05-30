---
title: "✅ARC085E"
---

![image](https://gyazo.com/c34c56dd50d7869ec0a4520a8a9c960c/thumb/1000)

[E - MUL](https://atcoder.jp/contests/arc085/tasks/arc085_c)
![image](https://gyazo.com/cb827e1c07c6b065c57300c21a9293d2/thumb/1000)
- Thoughts.
    - Known to be minimum cut entanglement
    - A matter of cutting, since there are two choices: to break or not to break.
    - N is 100
    - If a value is chosen, all multiples of that value must be divided
        - infinite cost side
    - There's a reward for the gems you didn't break.
        - If the reward is an edge cost, it's a maximum cut.
        - Think of it as "not getting paid" for the gems you split.
        - Minimize "unearned rewards."
        - ![image](https://gyazo.com/85f7ba7eefecb277f4cd69b70eda563d/thumb/1000)
    - If all rewards are positive, then the obvious solution is "don't break one".
        - have a negative side
        - How to handle it?
        - It should simply be offset, but what are the implications?
        - ![image](https://gyazo.com/b418f3fa2aaa035c2542326b0866c467/thumb/1000)
        - The value of the side is "profit when not broken" = "loss when broken".
            - Minimize losses
        - There is a negative loss when it is broken.
        - Wait? If this all turns out to be positive, it will still be cut off at the right of the S...
- Official Explanation
    - Negative loss when divided = gain when divided = cost when not divided
        - ![image](https://gyazo.com/3adfceb0bb32bfa1e60a3b9cb7cc1411/thumb/1000)
        - There was no need to separate the number of gems to be chosen from the number of gems to be divided.
            - I should have gone with "penalty if x is divided and a multiple of x is not divided."
- mounting
    - After finding the minimum cut, how do we get the value we want?
        - Minimizing the cut maximizes the score, so you'll be subtracting from some offset.
        - That offset was the "sum of prices that are positive" when I looked at the sample data, what is the logic behind this?
        - ![image](https://gyazo.com/ce05e85b83185144a9bd870534e1713b/thumb/1000)
        - The first basic rule is that "the reward you get if you don't break everything is the sum of the prices" and "by breaking, you incur a loss, and that loss is equal to the price" (left figure).
        - This is the basic premise, and then comes "I want to delete the negative sides because they are inconvenient for the calculation.
        - The vertex of 2 is either painted or not painted, so it should be +10 in either case (right figure).
        - The same paint job will cost 10 more than the figure on the left.
        - So increase the offset by 10 as well.
    - AC
python

```
def main():
    INF = 9223372036854775807
    N = int(input())
    AS = list(map(int, input().split()))
    offset = sum(max(0, x) for x in AS)
    d = Dinic(N + 2)
    start = N
    goal = N + 1
    for i in range(N):
        c = AS[i] 
        if c > 0:
            d.add_edge(i, goal, c)
        else:
            d.add_edge(start, i, -c)
        n = i + 1
        x = 2 * n
        while x <= N:
            d.add_edge(i, x - 1, INF)
            x += n

    print(offset - d.max_flow(start, goal))
```



---
This page is auto-translated from [/nishio/✅ARC085E](https://scrapbox.io/nishio/✅ARC085E) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
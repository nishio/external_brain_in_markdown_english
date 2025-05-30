---
title: "ABC172C"
---

Given two sequences of length 200,000 (A, B), the question is to answer the largest i+j such that the sum of the first i in A and the first j in B does not exceed the given number K.

Thoughts during the contest
- The problem statement says "Take one from the beginning of the number sequence...", is it OK if I take the smaller one?
    - A counterexample was found.
        - ![image](https://gyazo.com/e4691f605cbf81dd6aa75503417e1b7f/thumb/1000)
        - If it is required to be less than 6, the correct answer is 3,1,1,1 to make 6, but if you take 2 first, you get 2,3,1. This is not an optimal solution.
- The order in which they are taken is irrelevant.
    - Whether you take A and then B or vice versa, the calculation you do is "adding up", so it will be the same value.
        - [[I don't do them in the order of the problem statement.]]
- Let's check i+j in order from smallest to largest.
![image](https://gyazo.com/6fc6007792d68986558252292a22d018/thumb/1000)

after the contest
- Why not the above approach?
    - If the whole sequence of numbers is 1, and K is 500,000, then you have to check all the squares.
    - This requires 40 billion comparisons.

The right way to do it
![image](https://gyazo.com/f84276e6336eb5180864965deca093bb/thumb/1000)
- Start from the upper right corner
- If NG, go right.
    - Because it's over K and needs to be reduced more.
- If OK, proceed down.
    - Right from there is OK, but i+j is so small that there's no point in checking.
    - No need to do it from the right end.
        - Under NG is NG (if you're already over it, you're over it even if you increase it).
- At most N+M comparisons will ensure that you step on the rightmost OK square in each row.

python

```
def solve(N, M, K, sA, sB):
    max_can_read = 0
    last_max_j = M
    for i in range(N + 1):
        j = last_max_j
        while j >= 0:
            if sA[i] + sB[j] <= K:
                if max_can_read < i + j:
                    max_can_read = i + j
                last_max_j = j
                break
            j -= 1

    print(max_can_read)
```

AC [https://atcoder.jp/contests/abc172/submissions/14782042](https://atcoder.jp/contests/abc172/submissions/14782042)

[[atcoder]]

---
This page is auto-translated from [/nishio/ABC172C](https://scrapbox.io/nishio/ABC172C) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
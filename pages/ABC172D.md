---
title: "ABC172D"
---

![image](https://gyazo.com/d184857cee408b25e6ea65eb0d7f3799/thumb/1000)


[problem statement](https://atcoder.jp/contests/abc172/tasks/abc172_d)
If you think of the problem statement as it is written, the image is to calculate the number of divisors and then multiply by K and add them together [[Change the order of operations]]. [I don't do them in the order of the problem statement.
Multiplication is a repetition of addition, and addition does not change the result when the order is changed.
Counting the number of items that satisfy the condition" is also a process that takes the sum of "1 if the condition is satisfied and 0 if it is not satisfied.
So "K times K after counting" can be interchanged in order to "K, if the conditions are met, add up".
![image](https://gyazo.com/c5ad2bfbd34a616a96d2e65e5a7c4177/thumb/1000)

Once you have done this conversion, then [[warp and weft]]. The horizontal addition is Kf(K), and the answer you want to get is the sum of the two. Adding vertically first does not affect the result because of the exchange of addition order.
![image](https://gyazo.com/0d96d3c6ed540a523a4c41b8aff945c6/thumb/1000)
Vertical addition is [[Sum of isoperimetric sequences]], so you can get it out officially without turning the loop.
This is the way it's presented in the commentary
python

```
def solve(N):
    ret = 0
    for i in range(1, N + 1):
        num = N // i
        end = num * i
        ret += (i + end) * num // 2
    print(ret)
```

AC 1565 ms [https://atcoder.jp/contests/abc172/submissions/14787794](https://atcoder.jp/contests/abc172/submissions/14787794)

I will explore this issue later, as I have heard that there are two ways to do this, one with a smaller order and the other with a larger order but still manageable to get through.

By the way, this method of adding vertically adds one loop at a time, even though there is only one from halfway down anyway. If we add diagonally, we only need half a loop. However, if you are going to add diagonally...
![image](https://gyazo.com/8ce00ba56e9147b6791e01a708f97b66/thumb/1000)

Add diagonally to the top left corner tightly. Then the number of loops would be on the order of the root n.
![image](https://gyazo.com/eefa326a4a1e00751adbecea14d340fd/thumb/1000)

python

```
def solve(N):
    ret = 0
    i = 2
    while True:
        step = i // 2
        start = (i + 1) // 2 * step
        if start > N:
            break
        end = N // step * step
        ret += (start + end) * ((end - start) // step + 1) // 2
        i += 1
    print(ret)
```

AC 33 ms [https://atcoder.jp/contests/abc172/submissions/14788541](https://atcoder.jp/contests/abc172/submissions/14788541)
50 times faster.

[[atcoder]]

---
This page is auto-translated from [/nishio/ABC172D](https://scrapbox.io/nishio/ABC172D) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "AGC032B"
---

![image](https://gyazo.com/e76108ab5d4311843730df54423d5dc2/thumb/1000)

[B - Balanced Neighbors](https://atcoder.jp/contests/agc032/tasks/agc032_b)
- ![image](https://gyazo.com/3f912a7e570eb817ebab2122ec066518/thumb/1000)
- Thoughts.
    - 1,3,2 for 3
    - What if it's 4?
        - How should we think about it?
        - Total value is SN
        - Another way to count this is to distribute XY around the perimeter if the rank X and the value Y
        - That is, if the rank is Di
            - $\sum_i iD_i = SN$
        - When all ranks are 1, the left-hand side is 10 and the right-hand side is 4s
        - Adding one more edge increases the number of places by two.
        - If you want to go for 16, just connect 2 and 4.
        - 1,2,4,3
        - This is missing 1 and 3.
        - Connect these and you'll get 4 more, just fine.
    - What if it's 5?
        - S is greater than N
            - Otherwise, the vertex connected to N cannot wait for further edges because it will be N at that point, violating the condition of concatenation
                - The exception is when the network has N as a hub and the non-N sum is also N. This is only true when 3.
            - There is no vertex with rank 1.
                - →A
        - The only time it cycles is when 4.
            - Since a+c=c+e cannot be satisfied in a,b,c,d,e.
        - A: So it's not so much "where's the edge" as "where's not."
            - At 3, 1-2
            - At 4, 1-4, 2,3
            - At 5, the sum is 14-10 if it is a perfect graph.
                - 1-4, 2-3, all together make 10.
            - At 6, 20-15
                - 1-5, 2-4, oh, I got an extra 3.
                - To begin with, 15 is not a multiple of 6.
                - If you want to align to 12, 15 is -3.
                - Hmmm, not easy.
- Something to think about again after some time.
    - Consider the complete graph
    - The sum of the numbers of the adjacent vertices of each vertex is then $f(x)=\sum_i i - x$.
    - When N is even, if x and N+1-x are connected $f'(x)=\sum_i i - x - (N + 1 - x) = \sum_i i - (N + 1)$ and constant regardless of x
    - Odd times are a problem.
    - ![image](https://gyazo.com/e76108ab5d4311843730df54423d5dc2/thumb/1000)
    - If we connect x and N-x with respect to 1~N-1, we get $f'(x)=\sum_i i - x - (N - x) = \sum_i i - N$, constant regardless of x
    - For N $f(x) = \sum_i i - x = \sum_i i - N$, so still the same value
Official Explanation
    - [[Complementary Graphs for Connected Graphs]]
    - I got there after a lot of trouble, but I should have paid attention to the supplemental graph right away.

problem partitioning
    - [[Build one, problem.]]
    - [[Small constraint problem]]
    - [[connected graph]]

[[AGC032]]

---
This page is auto-translated from [/nishio/AGC032B](https://scrapbox.io/nishio/AGC032B) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
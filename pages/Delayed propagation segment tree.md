---
title: "Delayed propagation segment tree"
---

Data structure that combines value segment trees and action segment trees to allow range actions and range contractions

- Set of values V( [[monoid]] )
    - Binary $f(x, y) → z$where $x,y,z \in V$.
    - TABLE:Being a monoid
        - Binary operation [[associative law]] [[unit element]]
        - add	a + (b + c) = (a + b) + c	0	0 + x = x + 0 = x
        - mul	a * (b * c) = (a * b) * c	1	1 * x = x * 1 = 1
        - max	max(a, max(b, c)) = max(max(a, b), c)	-INF	max(-INF, x) = max(x, -INF) = x
    - This part has the same constraints as [[segment tree]].
    - Repeating binary operations on multiple values within a certain range to obtain a single value is called "[[range contraction]]".
- Action set A (action)
    - Action: $f(x) → y$ where $x,y \in V, f \in A$.
    - Composition of action: $c(f, g) → h$ where $f,g \in A, h(x) = g(f(x))$
:
| Action Synthesis of action Unit source |
| -- | -- | -- |
| add | c(add(a), add(b)) = add(a + b) | add(0) |
| chmin | c(chmin(a), chmin(b)) = chmin(min(a, b)) | chmin(INF) |
| set | c(set(a), set(b)) = set(a if b is None else b)  | set(None) |
    - Actions on multiple values within a range are called "[[range actions]]".
    - The action f can be implemented literally as a function object, but it is slow, so it is usually expressed as add(1) with an integer 1, etc.
        - We will call this integer the "action parameter" in the sense that it is a parameter for specifying the action
        - Implementation requires a function that takes the "value to be acted upon" and "action parameters" as arguments and returns the "value after the action".
        - We call this function action_force because it forces the evaluation of the delayed action.
        - I was confused for a while because many explanations in the world refer to "action," "action parameter," and "action forcing function" collectively as "action," instead of calling them by different names.
- 5 are required: binary operation of value, unit source of value, composite operation of action, action forcing function, and unit source of action
- When range contraction is not necessary and point acquisition is sufficient
    - The process of propagation from bottom to top in a binary operation becomes unnecessary.
        - No = value segment tree required
    - → [[Half-delayed segment tree]]
- If the score is obtained and the synthesis of the action is commutative
    - Commutative: $c(f, g) = c(g, f)$
        - Example: c(add(a), add(b)) = c(add(b), add(a)) = add(a + b)
        - It is valid for add and chmin, not for set.
    - At this time, there is no need to propagate the previous action down when adding an additional action
        - → [[dual segment tree]]

Regarding node size
- For example, if we force the action "increase by 1" on a node that has 4 leaves, the value will increase by 4
- If we try to do this in code, the action coercion function needs to take the size of the node as an argument
- It deviated from the mathematical structure and made me wonder.
- This is mathematically equivalent to
    - The set of values is not int but (int, size)
    - The leaf value is (int, 1)
- You can actually have a tuple of values as shown here and calculate the size with a binomial operation
- Size can be calculated from the ID of the node, so having no value can speed up the process.
- Some problems require size for binary operations on values.
    - [[ACL Beginner Contest]]

orthographical variants
    - [[Delayed Segment Trees]]
    - [[Delayed propagation segment tree]]

---
This page is auto-translated from [/nishio/遅延伝搬セグメント木](https://scrapbox.io/nishio/遅延伝搬セグメント木) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
Delayed propagation segment tree
> Two types of interval operations can be realized by using two simple segment trees side by side. In other words
>  Interval arithmetic / Interval summing
>  can be done.
[Segment tree types and their requirements - Rabbit Hutch](https://kimiyuki.net/blog/2017/01/17/segment-tree-requirements/)
- [On the notion of a dual segment tree - The Rabbit Hutch](https://kimiyuki.net/blog/2019/02/22/dual-segment-tree/)

[about delay propagation segment trees (formerly delay evaluation segment trees) - beet's soil](https://beet-aizu.hatenablog.com/entry/2017/12/01/225955)

- [[Delayed propagation segment tree]]
- [[Delayed Segment Trees]]
- [[segment tree]]
---
This page is auto-translated from [/nishio/遅延伝播segment木](https://scrapbox.io/nishio/遅延伝播segment木) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
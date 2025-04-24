---
title: "Deletable set with inequality condition"
---

requirement
- We want to enumerate from the deletable set $\{x\}$ those satisfying the condition $x \ge x_0$ expressed by the inequality sign
- For example, if [[sorted array]], [[dichotomous search]] can find the boundary satisfying the inequality condition in logarithmic order
    - But deleting from the array takes a linear order.
- Fast deletion [[linked list]] does not allow bisection search because random access is not possible

(key to) solution
    - Use [Fennic tree
- The value range is 0/1, representing the absence or presence of a value
- We can compute the sum s for the range below x0 in logarithmic order, and then bisect the points where the sum is s+1 in logarithmic order

- [[inequality sign condition]] in [[deletable set]]
- [[problem transformation]]

---
This page is auto-translated from [/nishio/削除可能集合で不等号条件](https://scrapbox.io/nishio/削除可能集合で不等号条件) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
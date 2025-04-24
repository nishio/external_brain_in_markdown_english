---
title: "Cost per unit"
---

![image](https://gyazo.com/c86c0724dfc3caed48081d4364b1be10/thumb/1000)
- Especially in business models where physical products are made in factories, the more units produced, the lower the cost per unit.
    - This is called [economies of scale
- However, "the bigger the scale, the lower the cost" is not always true.
    - In some cases, the processing cost per case increases as the amount of data increases, especially when it comes to information processing.

Simple example
- A customer comes to the receptionist and says his or her name. Based on that name, I want to retrieve that customer's information.
- How does the time cost of processing 100, 10,000, or 1,000,000 customers vary?
- A naive implementation (linear search) has a time cost proportional to the total number of customers N
- This is expressed as "it's an O(N) process" (order N)

It is known that the same objective can be achieved with O(log(N)) by devising an algorithm (order log N) see [Equilibrium Binary Search Tree](https://ja.wikipedia.org/wiki/平衡二分探索木)
- ![image](https://gyazo.com/d60a29ad43fdbddb48b359cf23af7e7d/thumb/1000)
- Complex algorithms often have high overhead, making them more expensive when data volumes are small.
- Which algorithm is appropriate to use depends on the amount of data in actual operation.
    - Choosing the right algorithm is an important design decision for business applications of information processing technology.

Why do these phenomena occur, especially with regard to information processing?
- The phenomenon of "costs going down as the scale increases" occurs when costs are shared among the products produced, regardless of the number of units.
- ![image](https://gyazo.com/0716315fb0c5832abd537ea5ffd551be/thumb/1000)
- For information processing, this cost is often a lower percentage of the overall cost than in equipment industries such as factories
    - For example, server costs are often not a fixed amount to begin with, but rather a service that can be flexibly increased or decreased based on customer volume, such as Amazon Elastic Compute Cloud (AWS EC2).
    - As a result, the relative "effect of lower costs due to increased scale" becomes smaller and less noticeable.

---
This page is auto-translated from [/nishio/1個あたりのコスト](https://scrapbox.io/nishio/1個あたりのコスト) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
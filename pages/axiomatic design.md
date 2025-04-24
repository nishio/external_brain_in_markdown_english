---
title: "axiomatic design"
---

![image](https://gyazo.com/61ebdb75951dec038d6d7641f78ffa63/thumb/1000)
- Axiomatic Design - Simplified Design of Complex Systems
    - [[NamPyo Suh]] (Author), Masayuki Nakao (Translator), Kenji Iino (Translator), [[Yotaro Hatamura]] (Translator)
- [Amazon](https://amzn.to/2EwFU8G)
- Original [Axiomatic Design Theory for Systems | SpringerLink](https://link.springer.com/article/10.1007/s001639870001)
    - [[Suh1998]]

- 1.6 Axiomatic and algorithmic approaches
- CA: Customer Attributes
- FR: Requested function
- C: Constraints
- DP: Design solution for entity domain
- PV: Process variable (production conditions in the process area)
![image](https://gyazo.com/407262cb7c8e2caaa4d54e0a27e79399/thumb/1000)


- Independence Axlom
    - FRs are defined as the minimum number of independent requirements that describe the design goals, and FR independence must be maintained at all times
- Information Axlom
    - The best design is the one with the least amount of information required in a design that satisfies the independence axiom.
    - In other words, the design with the highest probability of success is the best design(?).
    - Definition of information:.
        - ![image](https://gyazo.com/40483c4192e30285a36606a3be0e8e2e/thumb/1000)
        - In other words, the "information" he refers to is a value that is 0 when the probability of success is 1 and ∞ when it is 0

- The mapping from requirements function to design is represented by matrix A.
    - FR = A DP
    - Independent design when the matrix is a diagonal matrix, quasi-independent design when the matrix is a triangular matrix, and interference design otherwise.

- Axiom 1 (Independence Axiom): The design matrix must be of independent or quasi-independent design
- Axiom 2 (Information Axiom): The optimal design is the one with the least amount of information among designs that satisfy the independence axiom.




---
This page is auto-translated from [/nishio/公理的設計](https://scrapbox.io/nishio/公理的設計) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.
---
title: "matroid"
---

![image](https://gyazo.com/51f048871eb1073c9644717dffee67ff/thumb/1000)

- We say that (E, F) is a matroid when the family F of subsets of a set E satisfies a convenient property
- For maximization over matroids, [[greedy algorithm]] yields the optimal solution
- subset contained in F is "independent".
- F basically does not enumerate all (because that would be the same order as a full search).
    - Instead, it is sufficient to define a function "[[Oracle of Independence]]" that returns whether a subset is contained in F

Definition.
- A1: $\emptyset \in F$
- A2: $X \in F \Rightarrow \forall (Y \subset X) Y \in F$
    - Hereditary
    - If X is in F, then all subsets of X are also in F.
- A3: $X,Y \in F, |X| < |Y| \Rightarrow \exists x, x \in Y, x \notin X, X + \{x\} \in F$
    - If Y is larger, you can pick one and add it to X
    - Exchange Property Exchange Rules
    - ![image](https://gyazo.com/6f54763518ea15189443285f8a86a521/thumb/1000)
    - Note that it is not arbitrary x

The maximal independent sets (groups) to which no more elements can be added are all of the same size.

Example
- A set of vectors E and a family F of a set of first-order independent vectors
    - A2: A vector that is part of a linearly independent vector is linearly independent
    - A3: There is a vector in the higher order space Y that is first order independent of X
- A family of sets with less than or equal to a certain number of elements
    - uniform matroid
    - The figure at the beginning of this page shows a uniform matroid with less than 2 elements
- split matroid
    - Partitioning E into several sets and selecting at most one element from each set.
    - ![image](https://gyazo.com/c57edc9c7c64462d160d86b1a8f21fdb/thumb/1000)
- Edge set E of an undirected graph and F(forest) without closed path
    - closed circuit matroid
- The edge sets E and F of an undirected graph are [[pseudoforest]].
    - [Bicircular matroid - Wikipedia](https://en.wikipedia.org/wiki/Bicircular_matroid)




- [[matroid crossing]]
- [[The maximum matching of a bipartite graph is the matroid crossing of a partitioned matroid pair]]


Greed Law for Matroids


abc137d
[https://img.atcoder.jp/abc137/editorial.pdf](https://img.atcoder.jp/abc137/editorial.pdf)
Greed Law for Matroids
- attributed to [least-cost current

[https://ja.m.wikipedia.org/wiki/マトロイド](https://ja.m.wikipedia.org/wiki/マトロイド)
Surprisingly detailed

[https://app.mathsoc.jp/meeting_data/tokyo18mar/pdf/msjmeeting-2018mar-00f004.pdf](https://app.mathsoc.jp/meeting_data/tokyo18mar/pdf/msjmeeting-2018mar-00f004.pdf)
    - [[matroid crossing]]
    - [[incremental algorithm]]
    - The [[Maximum matching]] problem on [[2-part graph]] is a [[split matroid]] pair crossing problem
    - [Maximum Matching and Incremental Paths in Bipartite Graphs | Beautiful Stories in High School Mathematics](https://mathtrain.jp/bipartitematching)
    - [[principal dual algorithm]]
    - [[Primal-dual]]

[http://www.ieice-hbkb.org/files/12/12gun_02hen_05.pdf](http://www.ieice-hbkb.org/files/12/12gun_02hen_05.pdf)

[https://drken1215.hatenablog.com/entry/20121212/1355280288](https://drken1215.hatenablog.com/entry/20121212/1355280288)
[https://maspypy.com/atcoder-jsc2019予選-e-card-collector-](https://maspypy.com/atcoder-jsc2019予選-e-card-collector-) (Matroid)

---
This page is auto-translated from [/nishio/マトロイド](https://scrapbox.io/nishio/マトロイド) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.